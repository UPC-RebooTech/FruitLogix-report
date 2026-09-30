### 3.1.2. Information Architecture

La arquitectura de información de FruitLogix organiza el contenido y las funcionalidades de la Landing Page y de las aplicaciones móviles de acuerdo con las tareas principales de sus usuarios. La propuesta considera los segmentos de distribuidor, productor y cliente comercial, y busca que cada usuario pueda identificar rápidamente la información relevante para su rol.

A diferencia de la solución web previa, la propuesta actual prioriza experiencias móviles. Por ello, la organización, búsqueda y navegación se plantean para pantallas táctiles y recorridos orientados a tareas, evitando depender de estructuras propias de una aplicación de escritorio.

#### 3.1.2.1. Organization Systems

FruitLogix combina distintos sistemas de organización según el tipo de información y la tarea que realiza el usuario.

##### Organización visual del contenido

**Organización jerárquica (Visual Hierarchy).**  
Se aplica en pantallas de inicio, dashboards, detalles de pedidos, despachos, reportes de calidad y estados financieros. La información prioritaria, como el estado de un pedido, una alerta de telemetría, una incidencia o una deuda pendiente, debe presentarse antes que la información complementaria.

**Organización secuencial (Step-by-step).**  
Se aplica en procesos que requieren completar una serie de acciones en un orden determinado, como registrar un pedido, registrar una carga de cosecha, enviar información de calidad, validar un lote o completar una entrega. El objetivo es que el usuario comprenda qué paso está realizando y cuál es la siguiente acción disponible.

**Organización matricial.**  
Se utiliza cuando el usuario necesita comparar o filtrar varios registros, como pedidos, productores, cargas, lotes o despachos. En las aplicaciones móviles esta información se presenta principalmente mediante listas y cards adaptadas al tamaño de pantalla, en lugar de depender de tablas de escritorio.

##### Esquemas de categorización

**Por tópicos.**  
Las capacidades de FruitLogix se agrupan en áreas funcionales relacionadas con el dominio:

- Inicio / Dashboard
- Pedidos
- Productores y red de abastecimiento
- Catálogo y stock
- Calidad
- Logística, flota y tracking
- Incidencias
- Mensajes
- Facturación y pagos
- Perfil

Estas categorías representan áreas de contenido y no implican que todas deban mostrarse simultáneamente a todos los usuarios.

**Según audiencia.**  
La información y las acciones disponibles se adaptan al rol autenticado. Un distribuidor accede a capacidades relacionadas con pedidos, productores, calidad, flota, logística, incidencias y facturación; un productor prioriza cargas, stock, calidad y comunicación; mientras que un cliente comercial prioriza catálogo, pedidos, tracking, incidencias y estado financiero.

**Cronológica.**  
Se utiliza para historiales de pedidos, eventos de tracking, mensajes, incidencias y registros de calidad, permitiendo revisar la evolución de cada proceso en el tiempo.

**Alfabética.**  
Se utiliza de manera complementaria en listados donde el nombre constituye el principal criterio de reconocimiento, como productores, clientes o productos del catálogo.

#### 3.1.2.2. Labelling Systems

El sistema de etiquetado de FruitLogix utiliza términos breves, comprensibles y consistentes con el dominio del producto. Las etiquetas de interfaz se expresan desde la perspectiva del usuario, mientras que la implementación de código mantiene las convenciones técnicas definidas por el equipo.

##### Principios de etiquetado

**Simplicidad.**  
Las etiquetas utilizan el menor número de palabras necesario para comunicar una acción o contenido.

**Claridad.**  
Cada etiqueta debe expresar de forma directa su función y evitar términos ambiguos.

**Consistencia.**  
Una misma entidad o acción debe conservar la misma denominación a lo largo de la experiencia. Por ejemplo, se utilizará de forma consistente la etiqueta **“Pedidos”** para representar los pedidos gestionados por el usuario.

**Lenguaje del dominio.**  
Se utilizan términos reconocibles dentro de FruitLogix, como **Pedidos**, **Productores**, **Lotes**, **Calidad**, **Despachos**, **Incidencias**, **Stock** y **Facturación**.

##### Etiquetas principales

| Área | Etiquetas de referencia |
|---|---|
| General | Inicio, Perfil, Notificaciones, Mensajes |
| Pedidos | Pedidos, Nuevo pedido, Detalle del pedido, Historial |
| Productores | Productores, Invitar productor, Ficha del productor |
| Catálogo y stock | Catálogo, Productos, Stock, Nueva carga |
| Calidad | Calidad, Lote, Reporte de calidad, Aprobar, Rechazar |
| Logística | Despachos, Tracking, Flota, Ruta, Entrega |
| Incidencias | Incidencias, Reportar incidencia, Resolver |
| Finanzas | Facturación, Pagos, Balance |

##### Etiquetas de acciones

Las acciones se expresan mediante verbos directos, por ejemplo:

- Crear pedido
- Editar
- Eliminar
- Guardar
- Invitar
- Registrar carga
- Actualizar stock
- Enviar reporte
- Aprobar
- Rechazar
- Ver tracking
- Reportar incidencia
- Marcar como entregado
- Pagar
- Adjuntar archivo

Las acciones destructivas o irreversibles deben distinguirse visualmente y, cuando corresponda, requerir confirmación previa.

#### 3.1.2.3. SEO Tags and Meta Tags

La estrategia de SEO se aplica principalmente a la Landing Page pública de FruitLogix. Debido a que las aplicaciones móviles no dependen de indexación mediante motores de búsqueda web, para ellas se definen elementos ASO orientados a su futura publicación en tiendas de aplicaciones.

##### Landing Page

| Element | Value |
|---|---|
| **Title** | `FruitLogix | Gestión y trazabilidad para la distribución de frutas` |
| **Meta Description** | `FruitLogix centraliza la gestión de pedidos, calidad y seguimiento logístico para mejorar la trazabilidad en la cadena de distribución de frutas.` |
| **Keywords** | `logística agrícola, distribución de frutas, gestión de pedidos, control de calidad, trazabilidad, monitoreo de entregas, FruitLogix` |
| **Author** | `RebooTech` |

La Landing Page puede utilizar estas etiquetas como base general debido a que sus contenidos principales se organizan en secciones dentro de una experiencia pública orientada a presentar el producto.

##### ASO para las aplicaciones móviles

Se establece una base de ASO común para mantener una identidad coherente entre la aplicación nativa Android y la aplicación cross-platform. Los valores podrán ajustarse posteriormente según la tienda de distribución y el segmento funcional asignado a cada cliente móvil.

| Element | Native Android Application | Cross-Platform Mobile Application |
|---|---|---|
| **App Title** | `FruitLogix` | `FruitLogix` |
| **App Keywords** | `logística agrícola, pedidos, trazabilidad, calidad, frutas, entregas` | `logística agrícola, pedidos, trazabilidad, calidad, frutas, entregas` |
| **App Subtitle** | `Gestión móvil de la cadena de suministro` | `Gestión móvil de la cadena de suministro` |
| **App Description** | `Aplicación móvil de FruitLogix para gestionar y consultar procesos de pedidos, calidad, abastecimiento, seguimiento logístico y trazabilidad dentro de la cadena de distribución de frutas.` | `Aplicación móvil de FruitLogix para gestionar y consultar procesos de pedidos, calidad, abastecimiento, seguimiento logístico y trazabilidad dentro de la cadena de distribución de frutas.` |

#### 3.1.2.4. Searching Systems

Los sistemas de búsqueda de FruitLogix buscan reducir el tiempo necesario para localizar información dentro de las aplicaciones móviles. La búsqueda se incorpora únicamente en áreas donde el volumen de registros lo justifica y se complementa con filtros relacionados con la tarea del usuario.

##### Búsqueda y filtros

| Área | Opciones de búsqueda o filtrado |
|---|---|
| Pedidos e historial | Identificador, fecha, estado y productor |
| Productores | Nombre del productor |
| Catálogo / stock | Producto o tipo de fruta |
| Calidad | Lote y estado de validación |
| Logística | Despachos activos y estado de entrega |
| Incidencias | Estado de la incidencia |

Los filtros deben presentarse de manera progresiva para evitar sobrecargar las pantallas móviles. Cuando el usuario aplique criterios, la aplicación debe mostrar de forma visible qué filtros se encuentran activos.

##### Presentación de resultados

En las aplicaciones móviles, los resultados se presentan principalmente mediante listas verticales y cards que resumen la información esencial de cada elemento. Cada resultado puede conducir a una pantalla de detalle cuando sea necesario consultar información adicional.

La experiencia debe considerar:

- indicador de carga mientras se recupera información;
- mensaje claro cuando no existen resultados;
- conservación de la estructura visual aunque falte contenido secundario;
- actualización de resultados al aplicar o retirar filtros;
- posibilidad de limpiar los criterios aplicados.

#### 3.1.2.5. Navigation Systems

El sistema de navegación de FruitLogix se estructura según las tareas de cada tipo de usuario y las características del producto utilizado. La Landing Page utiliza navegación de exploración pública, mientras que las aplicaciones móviles utilizan navegación orientada a tareas y al rol autenticado.

##### Navegación de la Landing Page

La Landing Page utiliza una navegación superior hacia sus principales secciones:

- Inicio
- Beneficios
- Planes
- Clientes
- Testimonios

También incorpora acciones que permiten dirigir al visitante hacia la descarga o acceso a las aplicaciones de FruitLogix. Cuando corresponda, el visitante puede cambiar el idioma de la experiencia sin perder su ubicación dentro del contenido.

##### Navegación en las aplicaciones móviles

Las aplicaciones móviles mantienen una navegación jerárquica y orientada a tareas. Las áreas de uso frecuente se presentan como destinos principales y las acciones específicas se desarrollan en pantallas de detalle.

La navegación debe considerar:

- acceso rápido a las funciones principales del rol autenticado;
- navegación hacia pantallas de detalle desde listas o cards;
- retorno predecible a la pantalla anterior mediante los mecanismos de navegación de la plataforma;
- acciones contextuales dentro de pedidos, lotes, despachos, productores o incidencias;
- notificaciones que puedan conducir directamente al elemento relacionado cuando la funcionalidad lo requiera;
- conservación del estado de la tarea cuando el usuario navega entre pantallas relacionadas.

##### Recorridos principales por segmento

**Distribuidor**
`Inicio → Pedidos / Productores / Calidad / Logística → Detalle → Acción correspondiente`

Entre las acciones se encuentran registrar o gestionar pedidos, administrar productores, validar lotes, supervisar despachos, atender incidencias y consultar información financiera.

**Productor**
`Inicio → Cargas / Stock / Calidad → Registro o detalle → Enviar información`

El productor puede registrar cargas de cosecha, mantener actualizado su stock, registrar información de calidad y compartirla con el distribuidor.

**Cliente Comercial**
`Inicio / Catálogo → Pedido → Seguimiento → Recepción / Incidencia`

El cliente comercial puede explorar productos, consultar sus pedidos, visualizar tracking, revisar información de la entrega y registrar observaciones relacionadas con el servicio o la calidad.

La asignación definitiva de estos recorridos entre la aplicación nativa Android y la aplicación cross-platform se mantendrá alineada con la distribución funcional acordada por el equipo, conservando los mismos criterios de organización, etiquetado y navegación.
