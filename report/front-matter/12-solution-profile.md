## 1.2 Solution Profile

### 1.2.1 Antecedentes y problemática

En el Perú, uno de los principales problemas en la cadena de distribución de frutas no es solo la disponibilidad del producto, sino la eficiencia de su gestión logística. En Lima Metropolitana, se generan altas tasas de mermas y pérdidas alimentarias todos los días debido al uso generalizado de procesos manuales e informales como hojas de cálculo, cuadernos y aplicaciones de mensajería (Agraria, 2019). Esto hace que volúmenes significativos de producción agrícola que podrían comercializarse se pierdan antes de llegar al consumidor final, en lugar de aprovecharse como un recurso económico útil. Frente a esto, la Organización de las Naciones Unidas para la Alimentación y la Agricultura ha señalado que la digitalización y el monitoreo en tiempo real de la cadena de frío son alternativas fundamentales para enfrentar el desperdicio en la región (FAO, 2019). Sin embargo, en la práctica, su implementación en el mercado interno sigue siendo limitada, principalmente por la falta de herramientas tecnológicas accesibles que permitan estandarizar la calidad de los lotes e integrar a los actores de la cadena de suministro. Además, este escenario se ve exigido por las regulaciones del Ministerio de Salud mediante el Reglamento sobre Vigilancia y Control Sanitario de Alimentos y Bebidas, el cual establece la obligatoriedad de garantizar la inocuidad y la trazabilidad de los alimentos perecederos en los puntos de venta (Decreto Supremo N° 007-98-SA, 1998). En resumen, esto demuestra que existe una gran pérdida operativa en la gestión tradicional del sector agrícola. En el caso de la distribución de frutas, esto refuerza la necesidad de implementar soluciones tecnológicas centralizadas que permitan supervisar, monitorear y optimizar el flujo del producto desde el campo hasta el cliente comercial.

A continuación, se desarrollarán las preguntas clave usando el modelo de las 5W y 2H, ya que es importante para la identificación del problema y sus antecedentes.

| Preguntas | Pregunta formulada para el problema | Respuestas                                                                                                                                                                          |
|-----------|-------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Who?      | ¿Quiénes son los afectados?         | Distribuidores independientes medianos, productores agrícolas abastecedores y clientes comerciales (cadenas de retail, supermercados y restaurantes) en Lima Metropolitana.                                                                          |
| What?     | ¿Cuál es el problema?               | Gestión logística y control de calidad fragmentados mediante procesos manuales y no integrados, provocando desorden operativo, falta de trazabilidad y rechazos en la entrega.          |
| Where?    | ¿Dónde ocurre?                      | En la cadena de suministro agroalimentaria que conecta los centros de cultivo y acopio con los puntos de distribución y venta de Lima Metropolitana.               |
| When?     | ¿Cuándo sucede?                     | Durante el registro y confirmación de pedidos, la cosecha y clasificación del lote, el transporte en ruta y la recepción final con validación de calidad.                                        |
| Why?      | ¿Por qué ocurre?                    | Por la brecha de digitalización en el sector, la ausencia de una plataforma centralizada y la dependencia excesiva de canales informales (cuadernos, Excel y WhatsApp). |
| How?      | ¿Cómo se manifiesta?                | En pedidos despachados incorrectamente, pérdida de la cadena de frío sin monitoreo térmico, comunicación desincronizada y devoluciones de lotes en recepción.                    |
| How Much? | ¿Cuánto impacto tiene?              | Genera mermas y pérdidas de entre un 30% y 35% del volumen de productos frescos comercializados en el país debido a deficiencias en postcosecha, transporte sin monitoreo térmico y manipulación inadecuada, ocasionando sobrecostos logísticos, desperdicio de producto apto para la venta y frecuentes rechazos en los puntos de recepción (Agraria.pe, 2019).     |


### 1.2.2.1 Lean Ux Problem Statements

El estado actual de la logística agrícola y la cadena de suministro de frutas en el Perú se ha centrado principalmente en productores, distribuidores medianos y clientes comerciales (supermercados, mercados mayoristas y restaurantes) que coordinan sus operaciones mediante procesos manuales como hojas de cálculo, registros en papel y aplicaciones de mensajería, lo que genera desorganización en la gestión de pedidos, falta de trazabilidad durante la distribución y retrasos que afectan la calidad del servicio y la toma de decisiones.

Lo que los productos/servicios existentes no logran resolver es la falta de coordinación y monitoreo en tiempo real entre productores, distribuidores y clientes comerciales, lo que impide anticipar y prevenir pérdidas de calidad en productos perecederos, y responder a imprevistos antes de que el producto llegue al cliente final.

Nuestro producto/servicio abordará esta brecha centralizando la gestión de pedidos, el control de calidad y la trazabilidad en tiempo real de las entregas, integrando en una sola plataforma digital la comunicación entre productores, distribuidores y clientes comerciales.

Nuestro enfoque inicial será los distribuidores medianos de Lima Metropolitana que abastecen a supermercados, mercados mayoristas y restaurantes.

Sabremos que tenemos éxito cuando observemos una reducción del 30% en los errores operativos y del 25% en los pedidos rechazados por problemas de calidad, durante los primeros seis meses de uso de la plataforma.

### 1.2.2.2. Lean UX Assumptions

#### Business Assumptions

- Creemos que existe un mercado desatendido de distribuidores medianos en Lima Metropolitana que pierden rentabilidad debido a procesos manuales e informales (cuadernos, Excel y WhatsApp) y que están dispuestos a adoptar una plataforma de gestión operativa.

- Creemos que la coordinación simultánea entre los encargados dentro de un único entorno digital representa una ventaja competitiva sostenible frente a ERPs costosos (SAP Agri) o directorios estáticos de precios (AgroData Perú).

- Creemos que aunque la resistencia al cambio cultural es la mayor barrera de entrada en el sector agrícola, una baja carga cognitiva en la interfaz facilitará que usuarios con alfabetización digital básica migren sus operaciones diarias a la plataforma.

#### Business Outcome Assumptions

- Creemos que lograremos reducir en un 30% los errores de registro, despacho y duplicidad durante los primeros seis meses. Sabremos que esto ocurrirá cuando al menos el 90% de los pedidos se registren directamente en la plataforma.

- Creemos que lograremos reducir en un 25% los pedidos rechazados por problemas de calidad. Sabremos que estaremos en lo correcto cuando los productores reportan el estado de calidad de cada lote antes del despacho en al menos el 80% de los envíos.

- Creemos que lograremos reducir en un 35% el tiempo promedio transcurrido entre la creación de una orden comercial y su confirmación/asignación de cosecha. Sabremos que se habrá logrado el objetivo cuando más del 75% de las asignaciones de pedidos se gestionan mediante las alertas automáticas de disponibilidad de la plataforma.

- Creemos que lograremos reducir en un 50% las consultas manuales de los clientes comerciales. Sabremos que esto será cierto cuando los clientes puedan consultar el estado y la trazabilidad de sus pedidos directamente desde la plataforma, reduciendo en un 50% las llamadas y mensajes de seguimiento.

#### User Assumptions

- Creemos que nuestro primer segmento son los productores de los insumos, es decir, agricultores y recolectores en zonas rurales y periurbanas que operan con tecnología móvil básica, clasifican su mercancía bajo criterios subjetivos y sufren pérdidas económicas al recibir notificaciones tardías de rechazo cuando su lote ya viajó a Lima.

- Creemos que nuestro segundo segmento son los
  distribuidores de insumos, correspondientes a los intermediarios logísticos independientes y jefes de almacén en Lima Metropolitana que centralizan pedidos con menos de 48 horas de anticipación, dependiendo de herramientas desconectadas (Excel, notas de papel y llamadas) para organizar rutas y stock sin visibilidad en tiempo real.

- Creemos que nuestro tercer segmento son los encargados de compras y cocina de negocios minoristas (supermercados, cadenas de restaurantes y juguerías), quienes gestionan múltiples proveedores al mismo tiempo y sufren incertidumbre sobre la frescura y la hora exacta de entrega de los insumos perecibles.

#### User Outcomes and Benefits

- Creemos que los distribuidores de frutas buscan visibilidad centralizada del stock disponible de productores y del progreso de la flota en ruta.

- Creemos que los productores agrícolas esperan recibir requerimientos con anticipación estructurada y formalizar la calidad de su producción antes del despacho.

- Creemos que los clientes comerciales quieren acceder al estado del pedido y a la estimación del tiempo de llegada (ETA) en tiempo real.

#### Feature Assumptions

- Creemos que un módulo centralizado de gestión de pedidos con reglas de asignación automática según stock y capacidad reducirá los errores de despacho y duplicidad en al menos un 30%.

- Creemos que la estandarización del control de calidad por Lotes (fichas técnicas digitales y respaldo fotográfico obligatorio previo al despacho) disminuirá los rechazos en destino en un 25%.

- Creemos que el monitoreo continuo de la cadena de frío mediante sensores IoT (temperatura y humedad) integrados al panel de rastreo logístico evitará pérdidas de producto durante el transporte en al menos un 20%.

- Creemos que un sistema de notificaciones proactivas y mensajería unificada vinculada a órdenes reducirá en más de un 50% la necesidad de realizar llamadas y mensajes dispersos de seguimiento entre los tres actores.

- Creemos que un dashboard de KPIs operativos y financieros permitirá a los administradores identificar cuellos de botella en la flota y conciliar cuentas por cobrar/pagar en tiempo real.

### Lean UX Hypotheses Statements

- Hipótesis 1 (Módulo centralizado de gestión de pedidos)

Creemos que lograremos reducir los errores de despacho y duplicidad en al menos un 30%

Si los distribuidores medianos y sus jefes de almacén

Obtienen un proceso de asignación automática que previene sobreventas y errores manuales de registro

Con un módulo centralizado de gestión de pedidos con reglas de asignación según stock y capacidad.

- Hipótesis 2 (Estandarización del control de calidad por lotes)

Creemos que lograremos disminuir los pedidos rechazados en destino en un 25%

Si los productores y distribuidores de frutas

Obtienen un mecanismo estandarizado para validar y respaldar la condición técnica de la fruta antes de que salga del origen

Con un sistema de control de calidad por lotes con fichas técnicas digitales y registro fotográfico obligatorio previo al despacho.

- Hipótesis 3 (Monitoreo de cadena de frío con sensores IoT)

Creemos que lograremos evitar pérdidas de producto por deterioro durante el transporte en al menos un 20%

Si los distribuidores e intermediarios logísticos

Obtienen alertas inmediatas ante variaciones perjudiciales de temperatura y humedad en la ruta

Con un sistema de monitoreo continuo de cadena de frío mediante sensores IoT integrados al panel de rastreo.

- Hipótesis 4 (Notificaciones proactivas y mensajería unificada)

Creemos que lograremos reducir en más de un 50% la necesidad de llamadas y chats dispersos de seguimiento

Si los productores, distribuidores y clientes comerciales

Obtienen un canal de comunicación centralizado e integrado al historial de cada orden

Con un sistema de notificaciones proactivas y mensajería unificada vinculada directamente a las órdenes de compra.

- Hipótesis 5 (Dashboard de KPIs operativos y financieros)

Creemos que lograremos mejorar la toma de decisiones operativas y financieras del negocio.

Si los administradores y distribuidores 

Obtienen claridad visual sobre los cuellos de botella logísticos y la conciliación de cuentas por cobrar y pagar

Con un dashboard interactivo de KPIs operativos y financieros integrado a la plataforma actualizados en tiempo real.

#### 1.2.2.4. Lean UX Canvas

| 1. Business Problem | 5. Solution Ideas                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | 2. Business Outcomes |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|
| La cadena de distribución de frutas entre productores, distribuidores y clientes comerciales opera de forma manual y descoordinada (Excel, papel, WhatsApp), lo que genera errores en pedidos, falta de trazabilidad, rechazos por calidad y retrasos en la entrega. Esto ocasiona costos logísticos elevados, pérdidas económicas por devoluciones y baja satisfacción del cliente final. | - Módulo centralizado de gestión de pedidos con asignación automática según stock y capacidad. <br><br> - Sistema de control de calidad por lotes mediante fichas técnicas digitales y registro fotográfico previo al despacho. <br> - Monitoreo de cadena de frío mediante sensores IoT integrados al panel de rastreo. <br><br> - Canal de comunicación unificado con notificaciones automáticas e historial por orden. <br><br> - Dashboard interactivo de KPIs para visibilidad de cuellos de botella y conciliación financiera. | - Creemos que lograremos reducir en un 30% los errores de registro, despacho y duplicidad durante los primeros seis meses. Sabremos que esto ocurrirá cuando al menos el 90% de los pedidos se registren directamente en la plataforma.<br><br> - Creemos que lograremos reducir en un 25% los pedidos rechazados por problemas de calidad. Sabremos que estaremos en lo correcto cuando los productores reportan el estado de calidad de cada lote antes del despacho en al menos el 80% de los envíos.<br> - Creemos que lograremos reducir en un 35% el tiempo promedio transcurrido entre la creación de una orden comercial y su confirmación/asignación de cosecha. Sabremos que se habrá logrado el objetivo cuando más del 75% de las asignaciones de pedidos se gestionan mediante las alertas automáticas de disponibilidad de la plataforma.<br><br> - Creemos que lograremos reducir en un 50% las consultas manuales de los clientes comerciales. Sabremos que esto será cierto cuando los clientes puedan consultar el estado y la trazabilidad de sus pedidos directamente desde la plataforma, reduciendo en un 50% las llamadas y mensajes de seguimiento. |

| 3. Users and Customers | 4. User Benefits | |
|------------------------|------------------|------------------|
| - Creemos que nuestro primer segmento son los productores de los insumos, es decir, agricultores y recolectores en zonas rurales y periurbanas que operan con tecnología móvil básica, clasifican su mercancía bajo criterios subjetivos y sufren pérdidas económicas al recibir notificaciones tardías de rechazo cuando su lote ya viajó a Lima.<br><br> - Creemos que nuestro segundo segmento son los distribuidores de insumos, correspondientes a los intermediarios logísticos independientes y jefes de almacén en Lima Metropolitana que centralizan pedidos con menos de 48 horas de anticipación, dependiendo de herramientas desconectadas (Excel, notas de papel y llamadas) para organizar rutas y stock sin visibilidad en tiempo real.<br><br> - Creemos que nuestro tercer segmento son los encargados de compras y cocina de negocios minoristas (supermercados, cadenas de restaurantes y juguerías), quienes gestionan múltiples proveedores al mismo tiempo y sufren incertidumbre sobre la frescura y la hora exacta de entrega de los insumos perecibles. | - Creemos que los distribuidores de frutas buscan visibilidad centralizada del stock disponible de productores y del progreso de la flota en ruta.<br><br> - Creemos que los productores agrícolas esperan recibir requerimientos con anticipación estructurada y formalizar la calidad de su producción antes del despacho.<br>- Creemos que los clientes comerciales quieren acceder al estado del pedido y a la estimación del tiempo de llegada (ETA) en tiempo real.|

| 6. Hypotheses                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | 7. What’s the most important thing we need to learn first?                                                                                                                                                                                                                                                                                                                                                 | 8.  What’s the least amount of work we need to do to learn that?                                                                                                                                                                                                                                                               |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| - Creemos que lograremos reducir los errores de despacho y duplicidad en al menos un 30% si los distribuidores medianos y sus jefes de almacén obtienen un proceso de asignación automática que previene sobreventas y errores manuales de registro con un módulo centralizado de gestión de pedidos con reglas de asignación según stock y capacidad.<br><br> - Creemos que lograremos disminuir los pedidos rechazados en destino en un 25% si los productores y distribuidores de frutas, obtienen un mecanismo estandarizado para validar y respaldar la condición técnica de la fruta antes de que salga del origen con un sistema de control de calidad por lotes con fichas técnicas digitales y registro fotográfico obligatorio previo al despacho.<br><br> - Creemos que lograremos evitar pérdidas de producto por deterioro durante el transporte en al menos un 20% si los distribuidores e intermediarios logísticos obtienen alertas inmediatas ante variaciones perjudiciales de temperatura y humedad en la ruta con un sistema de monitoreo continuo de cadena de frío mediante sensores IoT integrados al panel de rastreo.<br><br>- Creemos que lograremos reducir en más de un 50% la necesidad de llamadas y chats dispersos de seguimiento si los productores, distribuidores y clientes comerciales obtienen un canal de comunicación centralizado e integrado al historial de cada orden con un sistema de notificaciones proactivas y mensajería unificada vinculada directamente a las órdenes de compra.<br><br> - Creemos que lograremos mejorar la toma de decisiones operativas y financieras del negocio si los administradores y distribuidores obtienen claridad visual sobre los cuellos de botella logísticos y la conciliación de cuentas por cobrar y pagar con un dashboard interactivo de KPIs operativos y financieros integrado a la plataforma actualizados en tiempo real. | - Adopción en campo: ¿Los productores agrícolas registrarán fichas técnicas y fotos de calidad antes del despacho? <br><br> - Cambio de hábito: ¿Los compradores comerciales usarán el enlace/portal de rastreo en lugar de llamar o enviar mensajes por WhatsApp? <br><br> - Factibilidad técnica: ¿La conectividad en zonas de acopio rural permite la sincronización de datos en tiempo real? <br><br> - Impacto operativo: ¿La automatización del registro disminuye realmente los errores frente al uso de Excel? | - Prototipo de usabilidad (Figma): Evaluar con 5 productores si pueden completar el registro de calidad en menos de 3 minutos sin asistencia. <br><br> - Experimento Wizard of Oz: Compartir un enlace de seguimiento simulado con 2 supermercados durante 2 semanas para medir la reducción de llamadas informales. <br><br> - MVP Concierge: Operar 14 días con 1 distribuidor usando una herramienta No-Code (Airtable/formularios) para medir la tasa de error en despachos. |