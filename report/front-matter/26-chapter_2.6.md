## 2.6 Tactical-Level Domain-Driven Design

En este capítulo se formaliza la arquitectura de software del sistema FruitLogix a partir de los hallazgos identificados en el análisis del dominio y el mapeo de contextos estratégicos. El propósito fundamental es trasladar los requerimientos funcionales y las reglas de negocio hacia una estructura modular, desacoplada y escalable, capaz de garantizar la interoperabilidad fluida entre Productores Agrícolas, Distribuidores y Clientes Comerciales.

Para lograrlo, se adopta un enfoque guiado por los patrones tácticos de Domain-Driven Design (DDD) y una arquitectura de capas. Esta combinación aísla la lógica central del negocio de los detalles de infraestructura, frameworks y servicios externos como pasarelas de pago o APIs de mapas.


### 2.6.4. Quality Control

El Quality Control Context aísla el ciclo de evaluación técnica, auditoría paramétrica y resolución de disconformidades sobre lotes de fruta perecible. Su límite arquitectónico asegura que la lógica de inspección organoléptica, fisicoquímica y empaque permanezca desacoplada de la facturación y del seguimiento de rutas de entrega.
#### 2.6.4.1 Domain Layer

Las entidades indentificadas en este Bounded Context son:

**Aggregate Roots**:
- HarvestBatch: Gobierna el lote recolectado en campo, encapsulando productor, variedad, volumen en kilogramos, fecha y su ciclo transaccional mediante el objeto de valor BatchStatus (PENDING, APPROVED, REJECTED).
- Incident: Administra no conformidades y reclamos de calidad asociados a un lote (BatchId), gestionando descripción técnica, evidencias fotográficas y estado (IncidentStatus: OPEN, IN_REVIEW, RESOLVED).
- QualityInspection: Entidad auditable que centraliza la evaluación global del lote, orquestando de manera atómica sus entidades internas subordinadas.

**Entities**:
- VisualInspection: Entidad dependiente que encapsula los resultados de la apariencia externa (AppearanceRating), defectos visibles detectados y el porcentaje de desperdicio estimado (WastePercentage).
- TechnicalParameters: Entidad dependiente encargada de registrar métricas fisicoquímicas y ambientales directas: temperatura en grados Celsius, porcentaje de humedad relativa, nivel de pH y sólidos solubles en grados Brix (BrixDegrees).
- PreparationChecklist: Entidad dependiente que valida el cumplimiento operativo previo al despacho (limpieza en seco, confirmación de selección por calibre, inspección del material de embalaje y sellado final de cajas).

**Value Objects**:
- BatchStatus: Representa los estados permitidos del lote agrícola (PENDING, APPROVED, REJECTED).
- IncidentStatus: Representa los estados resolutivos de una incidencia (OPEN, IN_REVIEW, RESOLVED).
- AppearanceRating: Escala de calificación visual del estado físico del producto perecible.
- VisualDefects: Encapsula los indicadores booleanos de imperfecciones físicas (manchas, golpes/magulladuras, deformaciones y presencia de pudrición).
- WastePercentage: Cuantifica la proporción numérica calculada de desperdicio o merma en el lote inspeccionado.
- BrixDegrees: Modela la concentración de azúcares y nivel de madurez organoléptica de la fruta.

**Commands**:
- CreateHarvestBatchCommand y UpdateHarvestBatchStatusCommand.
- CreateIncidentCommand y UpdateIncidentStatusCommand.
- CreateQualityInspectionCommand. 

**Queries**:
- GetAllHarvestBatchesQuery.
- GetAllIncidentsQuery.
- GetQualityInspectionByBatchIdQuery.

**Domain Repositories**:
- IHarvestBatchRepository, IIncidentRepository, IQualityInspectionRepository.

#### 2.6.4.2 Interfaces Layer

Expone contratos HTTP RESTful documentados para ser consumidos por el Frontend y aplicaciones cliente.

**Controladores API**:
- HarvestBatchesController
- IncidentsController
- QualityInspectionsController.

**Resources (DTOs)**:
- HarvestBatchResource
- CreateHarvestBatchResource
- UpdateHarvestBatchStatusResource
- IncidentResource
- CreateIncidentResource
- UpdateIncidentStatusResource
- QualityInspectionResource
- CreateQualityInspectionResource.

**Assemblers (Mappers)**:
Clases estáticas de transformación limpia (HarvestBatchResourceAssembler, IncidentResourceAssembler, QualityInspectionResourceAssembler) que convierten entidades de dominio a Resources sin filtrar detalles internos del modelo.

#### 2.6.4.3 Application Layer

Implementa el patrón de segregación de responsabilidades mediante servicios dedicados de comandos y consultas, orquestando transacciones a través de la unidad de trabajo y repositorios.

**Command Services**:
HarvestBatchCommandService, IncidentCommandService, QualityInspectionCommandService (con sus interfaces públicas IHarvestBatchCommandService, etc.). 

**Query Services**:
HarvestBatchQueryService, IncidentQueryService, QualityInspectionQueryService (con sus interfaces públicas IHarvestBatchQueryService, etc.).

#### 2.6.4.4 Infrastructure Layer

Persistencia Relacional (EFC): Implementación de los repositorios sobre Entity Framework Core (HarvestBatchRepository, IncidentRepository, QualityInspectionRepository).

Mapeo de Owned Entities: En el contexto de datos, QualityInspection mapea a VisualInspection, TechnicalParameters y PreparationChecklist como entidades dependientes ligadas a la misma transacción mediante la clave foránea asignada tras la creación del Aggregate Root.

#### 2.6.4.5 Bounded Context Software Architecture Component Level Diagram

<img alt="QualityControlComponentDiagram" height="200%" src="../assets/software_diagrams/C4_Component_Diagram_Quality_Control.png"/>

El diagrama de componentes del Quality Control Context ilustra la arquitectura interna del Quality Control Context dentro de la API backend, modelada bajo un enfoque de rebanadas verticales (vertical slices) centradas en el dominio. En este diseño, la aplicación móvil empleada por productores e inspectores en campo interactúa mediante peticiones HTTPS/JSON con tres componentes modulares que encapsulan la lógica transaccional de sus respectivos Aggregates de negocio: Harvest Batch Management, encargado del ciclo de vida y trazabilidad de los cargamentos recolectados; Quality Inspection Engine, responsable de coordinar y evaluar de manera atómica las mediciones fisicoquímicas, listas de empaque y defectos visuales; y Quality Incident Handling, enfocado en registrar reclamos y evidencias fotográficas para aplicar restricciones preventivas sobre lotes observados. Finalmente, estos componentes colaboran internamente para sincronizar los estados de aptitud comercial del producto y se comunican con el motor de base de datos relacional mediante Entity Framework Core, garantizando persistencia aislada, alta cohesión y un desacoplamiento estricto frente a las operaciones comerciales del sistema.

#### 2.6.4.6 Bounded Context Software Architecture Code Level Diagram

##### 2.6.4.6.1 Bounded Context Domain Layer Class Diagram

<img alt="QualityControlClassDiagram" height="200%" src="../assets/software_diagrams/Diagrama_Clases_Quality_Control.png"/>

El diagrama de clases de la capa de dominio detalla la estructura estática y las reglas tácticas del Quality Control Context estructuradas bajo los principios de Domain-Driven Design y Clean Architecture. En el paquete superior de repositorios se declaran las interfaces de persistencia (IHarvestBatchRepository, IIncidentRepository e IQualityInspectionRepository), las cuales definen contratos asíncronos para desacoplar las operaciones de lectura y escritura respecto a la infraestructura relacional. En el núcleo del modelo, el Aggregate Root HarvestBatch gobierna la identidad y los estados operativos del lote (BatchStatus), mientras que Incident administra las no conformidades y enlaces de evidencias fotográficas bajo su propio ciclo de resolución (IncidentStatus), referenciando al cargamento de forma débil mediante el identificador primitivo BatchId. Por su parte, la entidad QualityInspection implementa el contrato de trazabilidad temporal IAuditableEntity y compone de forma exclusiva a las entidades subordinadas TechnicalParameters, VisualInspection y PreparationChecklist. Finalmente, el paquete inferior aísla los objetos de valor inmutables (AppearanceRating, VisualDefects, WastePercentage y BrixDegrees), asegurando la encapsulación rigurosa de las validaciones fisicoquímicas y organolépticas requeridas durante la evaluación de la fruta.
