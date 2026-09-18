## 2.6 Tactical-Level Domain-Driven Design

En este capítulo se formaliza la arquitectura de software del sistema FruitLogix a partir de los hallazgos identificados en el análisis del dominio y el mapeo de contextos estratégicos. El propósito fundamental es trasladar los requerimientos funcionales y las reglas de negocio hacia una estructura modular, desacoplada y escalable, capaz de garantizar la interoperabilidad fluida entre Productores Agrícolas, Distribuidores y Clientes Comerciales.

Para lograrlo, se adopta un enfoque guiado por los patrones tácticos de Domain-Driven Design (DDD) y una arquitectura de capas. Esta combinación aísla la lógica central del negocio de los detalles de infraestructura, frameworks y servicios externos como pasarelas de pago o APIs de mapas.

### 2.6.1. Bounded Context: Profiles Management

El Profiles Management Context administra los perfiles de los actores agrícolas en FruitLogix, enfocándose principalmente en la gestión integral de los productores (Producer). Su frontera arquitectónica aísla la información legal, operativa, de contacto y de producción del agricultor respecto a los contextos transaccionales y de transporte.

#### 2.6.1.1 Domain Layer

Las entidades e identificadores en este Bounded Context son:

**Aggregate Roots**:

- Producer: Gobierna el perfil del productor, sus credenciales tributarias, ubicación geográfica, detalles de contacto y capacidad productiva.

**Value Objects**:

- TaxId: Encapsula el número de identificación fiscal (RUC/NIT) con reglas de validación de formato.

- ContactInfo: Agrupa los canales de comunicación principal (teléfono, correo electrónico, persona de contacto).

- Location: Estructura la dirección física, departamento, provincia y coordenadas de las instalaciones.

- ProductionInfo: Define la capacidad operativa, hectáreas de cultivo, tipos de fruta producida y certificaciones.

- ProducerType: Enumeración que clasifica el tipo de productor (e.g., Smallholder, MediumCommercial, ExportCooperative).
**Repositories**:

- IProducerRepository: Contrato de persistencia para las operaciones del agregado Producer.
- 
**Commands**:

- CreateProducerCommand

- UpdateProducerCommand

**Queries**:

- GetAllProducersQuery

- GetProducerByIdQuery

#### 2.6.1.2 Interfaces Layer

**Controladores API**:

- ProducersController: Expone los endpoints HTTP RESTful para el registro, actualización y consulta de productores.

**Resources (DTOs)**:

- CreateProducerResource

- UpdateProducerResource

- ProducerResource

**Assemblers (Mappers)**:

- ProducerResourceAssembler: Transforma los recursos DTO a comandos del dominio y mapea la entidad Producer hacia ProducerResource.

#### 2.6.1.3 Application Layer

**Command Services**:

- IProducerCommandService: Interfaz pública para procesar mutaciones.

- ProducerCommandService: Implementación de la lógica para procesar la creación y actualización de perfiles de productores.

**Query Services**:

- IProducerQueryService: Interfaz pública para lectura.

- ProducerQueryService: Implementación para coordinar las consultas de lectura (GetAllProducersQuery, GetProducerByIdQuery).

#### 2.6.1.4 Infrastructure Layer

**Persistencia Relacional (EFC)**:

- ProducerRepository: Implementación sobre Entity Framework Core encargada de la persistencia y mapeo relacional del agregado Producer y sus objetos de valor embebidos.


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

##### 2.6.4.6.2 Bounded Context Database Diagram

<img alt="QualityControlDatabaseDiagram" height="200%" src="../assets/software_diagrams/Diagrama_BaseDatos_Quality_Control.png"/>

El diagrama de base de datos relacional para el Quality Control Context modela la persistencia de las entidades y raíces de agregado garantizando integridad referencial y consistencia transaccional. La tabla principal HarvestBatches actúa como el pivote central del dominio, vinculándose mediante una relación de uno a muchos (1:N) con Incidents para el registro ilimitado de disconformidades y evidencias fotográficas sobre un lote. A su vez, se asocia de forma opcional y única (1:0..1) con QualityInspections, asegurando una auditoría formal consolidada por lote de cosecha. Por último, para reflejar fielmente la composición atómica del agregado, QualityInspections se descompone en tres tablas hijas especializadas (VisualInspections, TechnicalParameters y PreparationChecklists) conectadas bajo una cardinalidad estricta de uno a uno (1:1) mediante la clave foránea quality_inspection_id con restricción de unicidad, desacoplando limpiamente los parámetros fisicoquímicos, las listas de empaque y la evaluación organoléptica.


