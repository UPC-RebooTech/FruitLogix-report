## 4.2. Landing Page, Services & Applications Implementation.
En esta sección se describe el proceso de implementación del producto FruitLogix, incluyendo el desarrollo del sitio web estático, la integración de servicios y el despliegue de las aplicaciones; pues todas ellas constituyen etapas críticas del proyecto. Esta fase permite materializar los requerimientos técnicos y funcionales en código ejecutable, transformando conceptos iniciales en un producto robusto y orientado a satisfacer las necesidades de los usuarios objetivo.

### 4.2.1. Sprint 1
El primer sprint de nuestro proyecto posee una gran importancia en lo que refiere al proceso de desarrollo ágil. A lo largo de este periodo, se ha dado un enfoque con mayor énfasis en la implementación de componentes fundamentales para el producto, siendo estos la Landing Page, el Backend y una versión inicial de la aplicación móvil nativa.

#### 4.2.1.1. Sprint Planning 1.

La sesión de Sprint Planning tiene como fin analizar el rendimiento previo y establecer las metas técnicas de esta iteración. El equipo definirá y estimará las historias prioritarias del backlog para asignar responsabilidades. Esto garantizará la alineación operativa, una integración técnica continua y un plan de entrega bien estructurado

| Campo / Sección | Detalle |
| :--- | :--- |
| Sprint # | Sprint 1 |
| Sprint Planning Background | |
| Date | 2026-09-30 |
| Time | 4:00 PM |
| Location | Google Meet |
| Prepared By | Bojórquez Bustinza, Renzo Alejandro |
| Attendees (to planning meeting) | Bojórquez Bustinza, Renzo Alejandro / Chavez Bardales, Esteban Eduardo / Cochachi Chagua, Sebastián Josué / Marin Cueva, Cesar Fernando / Otiniano Rosales, Camila Alizée |
| Sprint Review Summary | Al tratarse del primer sprint, no se cuenta con iteraciones previas. En su lugar, el alcance y las metas se establecieron a partir de los requerimientos estructurados en el Product Backlog y los artefactos de diseño de la Landing Page desarrollados con anterioridad. |
| Sprint Retrospective Summary | No aplica para esta iteración. No obstante, el equipo estableció como compromiso transversal asegurar una distribución equitativa de las cargas de trabajo y fomentar una comunicación continua y transparente desde el inicio de la etapa de desarrollo. |
| Sprint 1 Goal | Nuestro enfoque se centra en establecer el canal de captación digital y habilitar el núcleo operativo de la plataforma conectando los flujos móviles clave con los servicios backend desplegados.<br>Creemos que esto entregará una Landing Page terminada y orientada a la conversión, un backend con al menos el 70% de sus funcionalidades base operativas en entorno de despliegue, y las pantallas core de la app móvil listas para la interacción del usuario.<br> Esto será confirmado cuando la Landing Page registre interacción en sus llamados a la acción y se demuestre un flujo operativo fluido en la aplicación móvil al comunicarse con la API desplegada. |
| Sprint 1 Velocity | El equipo ha establecido un Velocity de ## Story Points, que representa la capacidad máxima de esfuerzo que los developers pueden aceptar de manera realista para este Sprint 1. |
| Sum of Story Points | 132 |

#### 4.2.1.2 Aspect Leaders and Collaborators

En esta sección se define la matriz de liderazgo y colaboración (LACX) del Sprint 1, la cual permite identificar
claramente las responsabilidades de cada integrante del equipo en los distintos aspectos del desarrollo.

Para este sprint, los principales aspectos considerados están relacionados con la implementación del Landing Page, despliegue del backend, y creación de la primera versión de
la aplicación móvil.

| Team Member (Last Name, First Name) | GitHub Username | UX/UI Design | Landing Page | Documentation | Modeling |
|------------------------------------|----------------|-------------|-------------|--------------|----------|
| Bojórquez Bustinza, Renzo Alejandro | DeterminedSoul7 | C | C | C | L |
| Chavez Bardales, Esteban Eduardo | ECEB0704 | C | L | L | C |
| Cochachi Chagua, Sebastian Josue | sebastiancochachi02-cmd | C | C | C | C |
| Pinedo Sanchez, Sebastián Martín | Cmarin2802 | L | C | C | C |
| Otiniano Rosales, Camila Alizée | CamilaaAlizee | L | C | C | C |

#### 4.2.1.3 Sprint Backlog 1

El objetivo del presente Sprint fue el diseño y desarrollo de la landing page del sistema Aquanetix, enfocándose en la comunicación efectiva de la propuesta de valor, la presentación de funcionalidades clave y la facilitación del contacto con potenciales usuarios.

Durante este Sprint, el equipo trabajó de manera colaborativa en la construcción de las diferentes secciones de la landing page, asegurando una experiencia de usuario clara, intuitiva y alineada con los objetivos del sistema.

<div align="center">
  <img src="../assets/jira/Product_Backlog_Jira.png">

</div>

Enlace a la herramienta utilizada: [JIRA](https://rebootech-fruitlogix-202620.atlassian.net/jira/software/projects/SCRUM/boards/1/backlog?atlOrigin=eyJpIjoiOWFlZjE1OWMzMWU3NGMxOGJkYjM2ZDI2NmZhZTkyYTAiLCJwIjoiaiJ9)

A continuación, se detallan las User Stories priorizadas y las tareas asociadas:

| US Id | Title | Task Id | Task Title | Description | Estimation (Hours) | Assigned To | Status |
|---|---|---|---|---|---|---|---|
| US10 | Consultar historial de compras anteriores | SCRUM-68 | Consultar historial de compras anteriores | Muestra el listado de compras previas realizadas por el usuario con detalles y fechas. | 3 | Esteban Chavez| Done |
| US15 | Asignar vehículo y conductor a un despacho | SCRUM-72 | Asignar vehículo y conductor a un despacho | Permite vincular una unidad de transporte y un chofer asignado a una orden de despacho. | 3 |Esteban Chavez | Done |
| US18 | Consultar historial de despachos realizados | SCRUM-75 | Consultar historial de despachos realizados | Despliega el registro histórico de todos los envíos finalizados con sus estados. | 3 | Renzo Bojorquez| Done |
| US54 | Escaneo de código QR/barras en recepción de lote | SCRUM-92 | Escaneo de código QR/barras en recepción de lote | Habilita la lectura de códigos de barras o QR para validar la entrada de un lote. | 3 | Esteban Chavez| Done |
| US31 | Visualizar Landing Page | SCRUM-9 | Visualizar Landing Page | Pagina principal informativa de la plataforma orientada a usuarios no autenticados. | 2 |Esteban Chavez | Done |
| US33 | Visualización responsive del Landing Page | SCRUM-11 | Visualización responsive del Landing Page | Adaptación del diseño y componentes de la Landing Page para dispositivos móviles y tablets. | 2 | Esteban Chavez| Done |
| US32 | Navegar entre secciones del Landing Page | SCRUM-10 | Navegar entre secciones del Landing Page | Menú de navegación suave y accesos directos dentro de la Landing Page. | 1 |Esteban Chavez | Done |
| US02 | Iniciar sesión con credenciales | SCRUM-13 | Iniciar sesión con credenciales | Formulario de autenticación con correo y contraseña con validación de seguridad. | 2 | Cesar Marin | Done |
| US01 | Registrarse como cliente comercial | SCRUM-12 | Registrarse como cliente comercial | Formulario de registro para empresas o clientes comerciales para crear cuenta. | 3 |Cesar Marin | Done |
| US04 | Crear pedido de insumos | SCRUM-20 | Crear pedido de insumos | Interfaz para solicitar nuevos insumos seleccionando catálogo y cantidades. | 5 |Cesar Marin | Done |
| US07 | Visualizar estado del pedido | SCRUM-24 | Visualizar estado del pedido | Seguimiento en tiempo real de las fases y estado actual de una solicitud. | 3 | Cesar Marin | Done |
| TS05 | Implementar consulta de pedidos | SCRUM-25 | Implementar consulta de pedidos | Servicio backend y visualización de búsqueda filtrada de pedidos realizados. | 3 |Esteban Chavez | Done |
| US54 | Escaneo de código QR/barras en recepción de lote | SCRUM-28 | Escaneo de código QR/barras en recepción de lote | Módulo secundario/tarea para integración de la cámara en el escaneo de recepciones. | 3 |Esteban Chavez | Done |
| US43 | Monitorear flota en tiempo real | SCRUM-33 | Monitorear flota en tiempo real | Mapa interactivo con la ubicación en vivo de todos los vehículos de la flota. | 8 |Esteban Chavez | Done |
| US38 | Ver información del conductor en tracking | SCRUM-34 | Ver información del conductor en tracking | Ficha de información del chofer visible desde la vista de seguimiento del envío. | 3 |Esteban Chavez | Done |
| US56 | Geolocalización automática al marcar entrega | SCRUM-35 | Geolocalización automática al marcar entrega | Captura automática de coordenadas GPS en el instante que el repartidor confirma la entrega. | 3 | Esteban Chavez| Done |
| US46 | Ver detalle de despacho con telemetría | SCRUM-39 | Ver detalle de despacho con telemetría | Visualización gráfica de datos de telemetría (velocidad, ruta) asociados a un despacho. | 5 | Esteban Chavez| Done |
| US45 | Monitorear sensores IoT | SCRUM-40 | Monitorear sensores IoT | Panel de telemetría e indicadores en tiempo real capturados por sensores en ruta. | 8 | Renzo Bojorquez| Done |
| US12 | Ver reportes de calidad dinámicos | SCRUM-41 | Ver reportes de calidad dinámicos | Generación de gráficos y reportes interactivos sobre métricas de calidad de lotes. | 5 | Esteban Chavez| Done |
| US44 | Gestionar incidencias operativas | SCRUM-42 | Gestionar incidencias operativas | Panel para reportar, categorizar y dar seguimiento a problemas en la operación. | 5 | Esteban Chavez| Done |
| US57 | Nota de voz para reportar incidencias | SCRUM-43 | Nota de voz para reportar incidencias | Funcionalidad de grabación y envío de audio para registro rápido de novedades. | 5 | Camila Otiniano | Done |
| US55 | Sincronización automática de datos offline | SCRUM-45 | Sincronización automática de datos offline | Mecanismo que sincroniza datos guardados localmente cuando se recupera conexión. | 8 | Camila Otiniano | In Process |
| US53 | Formulario de inspección de campo offline | SCRUM-46 | Formulario de inspección de campo offline | Formulario de evaluación utilizable sin conexión a internet en zonas remotas. | 5 |Camila Otiniano | Done |
| US20 | Ver dashboard general de distribución | SCRUM-52 | Ver dashboard general de distribución | Panel centralizado con métricas clave y métricas de desempeño de la red de distribución. | 5 | Esteban Chavez| Done |
| US41 | Invitar productor a la red | SCRUM-53 | Invitar productor a la red | Envío de invitaciones vía correo/enlace para incorporar productores a la plataforma. | 3 | Camila Otiniano | Done |
| US47 | Gestionar facturación | SCRUM-60 | Gestionar facturación | Módulo para consultar, emitir y registrar comprobantes de pago/facturas. | 5 |Esteban Chavez | Done |
| US42 | Ver KPIs de gestión de productores | SCRUM-61 | Ver KPIs de gestión de productores | Métricas de rendimiento, cumplimiento y producción de cada productor registrado. | 5 |Esteban Chavez | Done |
| US13 | Configurar alertas de temperatura y humedad | SCRUM-70 | Configurar alertas de temperatura y humedad | Definición de umbrales límite para emitir notificaciones automáticas en transporte. | 3 |Esteban Chavez | Done |
| US17 | Registrar incidencia en la entrega | SCRUM-74 | Registrar incidencia en la entrega | Permite al transportista notificar contratiempos o daños al entregar el pedido. | 3 |Esteban Chavez | Done |
| US22 | Actualizar estado de un lote | SCRUM-77 | Actualizar estado de un lote | Modificación del estado actual de un lote en el flujo de procesamiento/cadena. | 2 |Esteban Chavez | Done |
| US27 | Configurar perfil de usuario | SCRUM-82 | Configurar perfil de usuario | Sección para editar datos personales, foto de perfil y preferencias de la cuenta. | 2 | Camila Otiniano | Done |
| SS01 | Integración de Telemetría IoT | SCRUM-93 | Integración de Telemetría IoT | Sección de Telemetría IoT | 8 |Renzo Bojorquez | Done |
| US08 | Filtrar catálogo  | SCRUM-66 | Filtrar catálogo por categoría y disponibilidad | Sección donde se filtra el catálogo por categoría y disponibilidad. | 2 |Cesar Marin | Done |
| US03 | Recuperar contraseña mediante correo  | SCRUM-31 | Recuperar contraseña mediante correo | Sección donde se puede recuperar contraseña mediante correo. | 3 |Cesar Marin | Done |


#### 4.2.1.4 Development Evidence for Sprint Review

En este Sprint se logró la implementación del Landing Page de FruitLogix, desarrollando su estructura principal en HTML y CSS, así como la navegación entre secciones y avances en su diseño responsive. De forma paralela, se avanzó en el desarrollo de la aplicación móvil en Android con Jetpack Compose, estructurando la arquitectura por Bounded Contexts e implementando módulos clave como la gestión de pedidos, facturación, monitoreo de infraestructura IoT, perfil de distribuidores, recepción logística y reporte de incidencias con grabación de audio.

El desarrollo se organizó mediante ramas de tipo feature en GitHub, permitiendo el trabajo coordinado e independiente en las distintas funcionalidades del ecosistema web y móvil. Los commits reflejan la construcción progresiva de las interfaces, la integración de lógica de dominio y el refinamiento de la experiencia de usuario.

A continuación, se presentan los commits más relevantes asociados al desarrollo del Sprint 1 para ambos repositorios.

| Repository | Branch | Commit Ids | Commit Message | Commit Message Body | Committed on (Date) |
|------------|--------|-----------|----------------|---------------------|---------------------|
| Fruitlogix-website | main | 1247d2895eb4c5a2f7ea4fd780f4f00fb5ca54a8 | chore: initial commit |  | 25/09/2026 |
| Fruitlogix-website | develop | 4f9d8344d561c1be443ff58bb1e874d80e6e85fa | fix: add APK download button to CTA section | Added a button to download the APK in the footer section. | 6/10/2026 |
|Fruitlogix-AppMobile  | main | 6bfa1959bf99b9e973187e353bf294f7f674e15a |chore: initial commit  |  | 2/10/2026 |
|Fruitlogix-AppMobile  | main  | 1f7e0009cf3f529a104d0ec32472463d9fbbedc5 | feat(bottom-navigation-more): update more button in bottom bar |  | 4/10/2026 |
| Fruitlogix-AppMobile | main | 0725fa8e00fc787de0b358ef7bef14cdccdfe10b | feat(order-management): implement order registration screen |  | 4/10/2026 |
|Fruitlogix-AppMobile  |  main | 9345654526bc0e6f5a7de236ab83a695bcb767ef|feat(order-management): implement order history screen|  | 4/10/2026 |
|Fruitlogix-AppMobile  | main | 8c9a5d39856f19e94d85c832c7bfb0cb85bc8861 | feat(payment-management): add billing domain and state|  |  4/10/2026|
|Fruitlogix-AppMobile  | main | bafe335bfba9c7930534f6e57d2d4994be335eca | feat(distributor-profile-management):implement distributor profile view and editing interface |  |5/10/2026  |
| Fruitlogix-AppMobile | main |  de42717db9c79c299d12135cca465ceb1a58e42c| feat(incident-report-audio): implement incident reporting with audio note recording and attachment |  | 5/10/2026 |
|Fruitlogix-AppMobile  | main | b07d2b446ddace7380f5b6a9cbe6d717b1e10eba | feat(logistics-arrivals): add inbound arrivals screen and geofence alert sheet |  |  5/10/2026|
|Fruitlogix-AppMobile  |main  |  0ad3befd9168ea2e2b57a534cc7e66cb62a5f927| feat(logistics-arrivals): add inbound arrivals screen and geofence alert sheet|  |  5/10/2026|
|Fruitlogix-AppMobile  | main|  93bb641ae1c6480b2d9517e04d853b95e4606add| refactor(payment-management): make invoice detail repository injectable |  |  5/10/2026|
|Fruitlogix-AppMobile  | main |  14993ab0c350e898bc880f825192f53d196f2812| feat(infrastructureIot):update strings for iot bounded context. |  |  5/10/2026|
|Fruitlogix-AppMobile  | main| b19edcd4913c75a1dd6855cafafdb314b52de051 | feat(infrastructureIot):implement sensors alerts ui state. |  |  5/10/2026|
|Fruitlogix-AppMobile  | main| f7dbafe6e437c5a4ead92bb53434f24ad03db5d6 | feat(fleet-drivers-vehicles): add drivers tab with driver cards, filters and license validity |  |  5/10/2026|

#### 4.2.1.5 Execution Evidence for Sprint Review

En esta sección se presentan evidencias de la ejecución de la landing page desarrollada durante el Sprint.

**Figura 1. Sección principal de la landing page**

<div align="center">
  <img src="../assets/LandingPage/Landing1.png">
</div>

**Figura 2. Sección beneficios**

<div align="center">
  <img src="../assets/LandingPage/Landing2.png">
</div>

**Figura 3. Sección de funcionalidades**

<div align="center">
  <img src="../assets/LandingPage/Landing3.png">
</div>

**Figura 4. Sección de clientes**

<div align="center">
  <img src="../assets/LandingPage/Landing5.png">
</div>

**Figura 5. Sección de testimonios**

<div align="center">
  <img src="../assets/LandingPage/Landing4.png">
</div>

**Figura 6. Sección de planes**

<div align="center">
  <img src="../assets/LandingPage/Landing6.png">
</div>

**Figura 7. Sección de del equipo**

<div align="center">
  <img src="../assets/LandingPage/Landing6.png">
</div>

**Figura 8. Sección final y llamado a la acción**

<div align="center">
  <img src="../assets/LandingPage/Landing8.png">
</div>



#### 4.2.1.6 Services Documentation Evidence for Sprint Review

En el presente Sprint no se implementaron Web Services ni endpoints backend funcionales, debido a que el alcance estuvo enfocado en la construcción de la primera versión del Landing Page estático y en el desarrollo de la arquitectura e interfaz gráfica del cliente móvil Android en Jetpack Compose.

Sin embargo, como parte del análisis de arquitectura e integración, se definieron los modelos de datos y la estructura de dominio necesaria para consumir futuros servicios RESTful. 
Estos servicios permitirán sincronizar la información del cliente móvil con los servidores de FruitLogix en iteraciones posteriores (incluyendo autenticación, sincronización offline de insumos e inspecciones de calidad, y descarga de reportes), los cuales serán documentados formalmente utilizando el estándar OpenAPI (Swagger) en los Sprints subsiguientes.

#### 4.2.1.7. Software Deployment Evidence for Sprint Review.

Para el Sprint 1, la estrategia de despliegue abarcó los dos entregables del ecosistema **FruitLogix**: la publicación del **Landing Page web estático** a través de GitHub Pages y la distribución de la **primera versión ejecutable de la aplicación móvil (APK de desarrollo)** para validación en dispositivos Android reales y simuladores.


### A. Despliegue de la Landing Page Web

El despliegue de la Landing Page de FruitLogix se realizó utilizando **GitHub Pages**, aprovechando sus capacidades para publicar sitios web estáticos de forma automatizada directamente desde el repositorio de código fuente.

* **Repositorio de código fuente:** GitHub (`Fruitlogix-website`)
* **Plataforma de despliegue:** GitHub Pages
* **Tipo de aplicación:** Landing Page estática (HTML5, CSS3, JavaScript)
* **URL de acceso público:** [https://github.com/UPC-RebooTech/Fruitlogix-website](https://github.com/UPC-RebooTech/Fruitlogix-website)

#### Proceso de Despliegue Web:
1. **Creación y Organización del Repositorio:** Se estructuró el repositorio en GitHub con los archivos web principales (`index.html`, hojas de estilo CSS y recursos multimedia), garantizando el correcto uso de rutas relativas.
2. **Subida de Código:** Se realizó el *push* a la rama principal (`main`) tras verificar la integridad de las secciones informativas y botones de acción.
3. **Configuración de GitHub Pages:** En la sección *Settings* del repositorio, se activó la opción de publicación de GitHub Pages asignando la rama `main` y la carpeta raíz (`/root`) como origen de la compilación.
4. **Publicación y Despliegue Continuo:** GitHub Pages procesó el repositorio y generó la URL pública de forma automática. Cada nuevo envío de cambios a la rama `main` actualiza la versión del sitio de forma transparente sin intervención manual.


### B. Despliegue y Distribución de la Aplicación Móvil (Android APK)

Para el cliente móvil de FruitLogix, se configuró la compilación nativa en Android Studio/Gradle para generar el paquete instalable binario (`.apk`), habilitando la prueba directa de las pantallas e interfaces construidas en Jetpack Compose.

* **Repositorio de código fuente:** GitHub (`Fruitlogix-AppMobile`)
* **Plataforma / Entorno de ejecución:** Android 8.0+ (API Level 26+)
* **Tecnología:** Kotlin / Jetpack Compose
* **Mecanismo de distribución:** Compilación de artefacto binario (`app-debug.apk`) y vinculación directa a los botones de descarga en la Landing Page web.
* **URL de acceso público:** [https://github.com/UPC-RebooTech/Fruitlogix-AppMobile.git](https://github.com/UPC-RebooTech/Fruitlogix-AppMobile.git)

#### Proceso de Despliegue Móvil:
1. **Compilación de Artefactos de Desarrollo:** Se ejecutó el proceso de construcción en Gradle (`./gradlew assembleDebug`) para empaquetar los recursos del proyecto, dependencias y la navegación por *Bounded Contexts*.
2. **Generación del APK Ejecutable:** Se obtuvo el binario instalable con los módulos activos de *Profiles Management*, *Quality Control*, *Order Management* y *Payment Management*.
3. **Distribución Integrada:** El archivo binario APK se alojó y vinculó a la sección *Call-to-Action* (CTA) y botones del Landing Page, permitiendo a los evaluadores y miembros del equipo descargar e instalar la aplicación en dispositivos móviles para las pruebas del Sprint Review.

#### 4.2.1.8. Team Collaboration Insights during Sprint

Para el desarrollo de este primer sprint, todos los miembros del equipo desarrollaron y colaboraron de manera activa y continua. De tal modo, se muestra como evidencia los insights de cada miembro del equipo.
<p align = "left">
   <img src="../assets/insights/Team Collaboration Insights.png">
</p>

### 4.2.2. Sprint 2
El segundo sprint del proyecto marca un punto clave de evolución e integración en el ecosistema **FruitLogix**. A lo largo de esta iteración, el equipo se enfocó en renovar y desplegar la nueva versión de la **Landing Page** (incorporando el video de presentación del equipo y mejoras visuales tras las primeras validaciones), consolidar las funcionalidades operativas de la **aplicación móvil nativa en Android (Jetpack Compose)** para los roles de **Productor Agrícola y Distribuidor Comercial** conectadas al backend, e iniciar el desarrollo de la primera versión de la **aplicación multiplataforma en Flutter** orientada específicamente a los **Clientes Comerciales**.

#### 4.2.2.1. Sprint Planning 2.

La sesión de Sprint Planning 2 tuvo como finalidad evaluar los resultados obtenidos durante el primer sprint, revisar las observaciones recogidas en la retrospectiva y definir los compromisos técnicos de esta segunda iteración. Durante la reunión, se priorizaron las historias de usuario vinculadas a la integración entre productores y distribuidores, el lanzamiento de la versión renovada del sitio web y el arranque del cliente multiplataforma en Flutter.

| Campo / Sección | Detalle |
| :--- | :--- |
| Sprint # | Sprint 2 |
| Sprint Planning Background | |
| Date | 2026-10-15 |
| Time | 4:00 PM |
| Location | Google Meet |
| Prepared By | Otiniano Rosales, Camila Alizée |
| Attendees (to planning meeting) | Bojórquez Bustinza, Renzo Alejandro / Chavez Bardales, Esteban Eduardo / Cochachi Chagua, Sebastián Josué / Marin Cueva, Cesar Fernando / Otiniano Rosales, Camila Alizée |
| Sprint Review Summary | En el Sprint 1 se entregó la primera versión funcional de la Landing Page y la estructura base de la aplicación nativa en Android con Jetpack Compose. No obstante, quedaron pendientes la integración completa de los flujos de comunicación y gestión de pedidos del productor con el backend, la renovación visual de la Landing Page y el desarrollo del módulo multiplataforma para clientes comerciales. |
| Sprint Retrospective Summary | El equipo identificó la necesidad de mejorar la sincronización de estados entre las interfaces móviles y los servicios desplegados, así como de estandarizar las ramas de trabajo en GitHub (`feature/*`, `develop`, `release/*`). Como acción de mejora, se acordó realizar revisiones cruzadas de código (Code Reviews) antes de cada merge y unificar la paleta visual en ambas aplicaciones móviles. |
| Sprint 2 Goal | Nuestro enfoque se centra en consolidar la experiencia operativa entre productores y distribuidores en la app Android nativa, publicar la nueva versión de la Landing Page y habilitar el núcleo funcional de la primera versión de la aplicación multiplataforma en Flutter para clientes comerciales.<br>Creemos que esto entregará un ecosistema sincronizado donde los productores puedan aceptar y coordinar pedidos conectados al backend, una Landing Page actualizada con mayor claridad en su propuesta de valor, y una app en Flutter con catálogo comercial y gestión inicial de órdenes.<br>Esto será confirmado cuando se verifique la comunicación fluida entre las pantallas de productor/distribuidor y la API, el despliegue público de la nueva Landing Page y la compilación estable de la primera versión de la app Flutter. |
| Sprint 2 Velocity | El equipo ha establecido un Velocity de 115 Story Points, ajustado de manera realista según el rendimiento observado en el Sprint 1 y la complejidad de abordar simultáneamente el entorno nativo Android y el multiplataforma en Flutter. |
| Sum of Story Points | 115 |

#### 4.2.2.2 Aspect Leaders and Collaborators

En esta sección se define la matriz de liderazgo y colaboración (LACX) del Sprint 2, la cual permite identificar claramente las responsabilidades asignadas a cada integrante del equipo en los distintos frentes de desarrollo de esta iteración. 

Para este sprint, los aspectos principales contemplan la renovación de la Landing Page, la integración de servicios backend para el flujo de productores y distribuidores en la app nativa, y el desarrollo de la primera versión del cliente multiplataforma en Flutter.

| Team Member (Last Name, First Name) | GitHub Username | UX/UI Design | Landing Page | Documentation | Modeling |
|------------------------------------|----------------|-------------|-------------|--------------|----------|
| Bojórquez Bustinza, Renzo Alejandro | DeterminedSoul7 | C | C | C | L |
| Chavez Bardales, Esteban Eduardo | ECEB0704 | C | L | L | C |
| Cochachi Chagua, Sebastian Josue | sebastiancochachi02-cmd | C | C | L | C |
| Marin Cueva, Cesar Fernando | Cmarin2802 | L | C | C | C |
| Otiniano Rosales, Camila Alizée | CamilaaAlizee | L | C | C | C |

#### 4.2.2.3 Sprint Backlog 2

El objetivo del presente Sprint se centró en la actualización y despliegue de la nueva versión de la Landing Page, la integración de las pantallas operativas de productores con el backend (gestión de lotes y chat contextual), así como el desarrollo inicial de la aplicación multiplataforma en Flutter orientada a los clientes comerciales.

Durante este Sprint, el equipo trabajó de manera colaborativa para asegurar la sincronización de los flujos móviles y servicios backend clave.

<div align="center">
  <img src="../assets/jira/Product_Backlog_Jira_Sprint2.png">
</div>

Enlace a la herramienta utilizada: [JIRA](https://rebootech-fruitlogix-202620.atlassian.net/jira/software/projects/SCRUM/boards/1/backlog)

A continuación, se detallan las User Stories priorizadas y las tareas asociadas:


| US Id | Title | Task Id | Task Title | Description | Estimation (Hours) | Assigned To | Status |
|---|---|---|---|---|---|---|---|
| US19 | Ver dashboard operativo del Productor | SCRUM-51 | US19: Ver dashboard operativo del Productor | Panel principal del productor con resumen de pedidos pendientes, lotes activos y métricas. | 5 | Sebastián Cochachi | Done |
| US48 | Registrar carga de cosecha | SCRUM-16 | US48: Registrar carga de cosecha | Interfaz y servicio para que el productor registre el volumen cosechado disponible. | 5 | Sebastián Cochachi | Done |
| US49 | Gestionar stock de productos | SCRUM-18 | US49: Gestionar stock de productos | Actualización y control de inventario disponible en fundo por variedad y calibre. | 3 | Camila Otiniano | Done |
| US21 | Registrar nuevo lote de producción | SCRUM-76 | US21: Registrar nuevo lote de producción | Formulario de alta de nuevos lotes agrícolas listos para comercialización. | 3 | Sebastián Cochachi | Done |
| US24 | Consultar historial de lotes producidos | SCRUM-79 | US24: Consultar historial de lotes producidos | Listado histórico de lotes cosechados y despachados por el productor. | 3 | Esteban Chavez | Done |
| US40 | Eliminar productor de la red | SCRUM-55 | US40: Eliminar productor de la red | Opción administrativa para dar de baja o desvincular a un productor del directorio. | 1 | Cesar Marin | Done |
| US25 | Enviar mensajes en el chat de un pedido | SCRUM-80 | US25: Enviar mensajes en el chat de un pedido | Canal de mensajería contextual vinculado a cada orden para coordinación logística. | 3 | Renzo Bojorquez | Done |
| US26 | Ver historial de mensajes | SCRUM-81 | US26: Ver historial de mensajes | Consulta del registro de conversaciones previas asociadas a cada despacho. | 2 | Cesar Marin | Done |
| US34 | Explorar catálogo con renders de alta fidelidad | SCRUM-15 | US34: Explorar catálogo con renders de alta fidelidad | Visualización interactiva del catálogo comercial de frutas en la primera versión Flutter. | 5 | Renzo Bojorquez | Done |
| US06 | Confirmar pedido y seleccionar método de pago | SCRUM-22 | US06: Confirmar pedido y seleccionar método de pago | Flujo inicial de confirmación de orden y selección de método de pago en Flutter. | 3 | Esteban Chavez | Done |
| US36 | Visualizar balance financiero en Dashboard del Cliente | SCRUM-59 | US36: Visualizar balance financiero en Dashboard del Cliente | Tarjetas de resumen con balance financiero y estado de órdenes en Flutter. | 5 | Sebastián Cochachi | Done |
| TS03 | Implementar registro de usuarios | SCRUM-7 | TS03: Implementar registro de usuarios | Endpoint y flujo de creación de cuentas para los distintos roles de la plataforma. | 3 | Camila Otiniano | Done |
| TS02 | Implementar autenticación de usuarios | SCRUM-8 | TS02: Implementar autenticación de usuarios | Validación de credenciales y generación de tokens de acceso seguro. | 3 | Renzo Bojorquez | Done |
| TS04 | Implementar registro de pedidos | SCRUM-19 | TS04: Implementar registro de pedidos | Lógica backend y persistencia para la creación de nuevas órdenes comerciales. | 5 | Camila Otiniano | Done |
| TS06 | Implementar actualización de estado de pedido | SCRUM-26 | TS06: Implementar actualización de estado de pedido | Sincronización de cambios de estado entre las pantallas de productor, distribuidor y backend. | 3 | Camila Otiniano | Done |
| TS10 | Implementar generación de reportes | SCRUM-62 | TS10: Implementar generación de reportes | Servicio backend para la consolidación y emisión de reportes operativos. | 5 | Renzo Bojorquez | Done |
| TS07 | Implementar registro de control de calidad | SCRUM-29 | TS07: Implementar registro de control de calidad | Endpoint y persistencia para el almacenamiento de evaluaciones de calidad de lotes. | 3 | Sebastián Cochachi | Done |
| US50 | Enviar reporte de calidad al distribuidor con fotos | SCRUM-30 | US50: Enviar reporte de calidad al distribuidor con fotos | Envío digital de fichas de inspección de calidad adjuntando evidencia fotográfica. | 5 | Renzo Bojorquez | Done |
| TS09 | Implementar envío de notificaciones | SCRUM-48 | TS09: Implementar envío de notificaciones | Servicio backend para despachar alertas de actualización de pedidos y despachos. | 5 | Esteban Chavez | Done |
| US39 | Editar ficha técnica de producto | SCRUM-54 | US39: Editar ficha técnica de producto | Edición de especificaciones de calidad, calibres y requerimientos de frío del lote. | 3 | Camila Otiniano | Done |
| US14 | Exportar historial de telemetría a PDF/Excel | SCRUM-71 | US14: Exportar historial de telemetría a PDF/Excel | Descarga del registro histórico de temperatura y ruta en formatos de reporte estándar. | 3 | Renzo Bojorquez | Done |
| US16 | Confirmar entrega mediante firma digital o código QR | SCRUM-73 | US16: Confirmar entrega mediante firma digital o código QR | Validación digital en destino al momento de recibir la mercadería del despacho. | 3 | Esteban Chavez | Done |
| US28 | Configurar preferencias de notificaciones push | SCRUM-83 | US28: Configurar preferencias de notificaciones push | Ajustes de usuario para habilitar o filtrar alertas operativas en el dispositivo móvil. | 2 | Renzo Bojorquez | Done |
| US30 | Cerrar sesión de forma segura | SCRUM-85 | US30: Cerrar sesión de forma segura | Limpieza de credenciales locales y finalización segura de la sesión activa. | 1 | Sebastián Cochachi | Done |

#### 4.2.2.4 Development Evidence for Sprint Review

Durante el Sprint 2, el desarrollo del ecosistema **FruitLogix** se organizó mediante ramas de características (`feature/*`) y flujo continuo (`develop` / `main`) en GitHub a través de tres repositorios clave: la aplicación móvil nativa en Android con Jetpack Compose (`Fruitlogix-AppMobile`), consolidando los módulos de productores, distribuidores y conectividad híbrida con Retrofit; la aplicación multiplataforma en Flutter (`Fruitlogix-Multiplatform`) orientada a clientes comerciales y gestión de pagos; y la nueva versión de la Landing Page (`Fruitlogix-website-v2`).

A continuación, se presentan los commits más relevantes asociados al desarrollo de los tres repositorios en este sprint:

| Repository | Branch | Commit Ids | Commit Message | Commit Message Body | Committed on (Date) |
|------------|--------|-----------|----------------|---------------------|---------------------|
| Fruitlogix-AppMobile | develop | 5f364ed14d60778a756175269c79c7e627683447 | feat(backendProducers): integrate hybrid offline-first architecture with Retrofit and local repositories |  | 11/11/2026 |
| Fruitlogix-AppMobile | feature/distributor-ui-redesign | 3dc2d342de0d4d06df7f09f6cf02110d05b9445d | feat(distributor-ui-redesign): redesign distributor home and order management |  | 12/11/2026 |
| Fruitlogix-AppMobile | feature/producer-messaging-chat | c8121a10b39ca1a9e053acfe1b2944d6856b5ece | feat(orderManagement): implement dynamic messaging inbox and bubble chat screen. |  | 07/11/2026 |
| Fruitlogix-AppMobile | feature/profiles-management | 1dcf869bc2ea66499e0216b4dd008cb4d7c8e0d4 | feat(profiles-management): complete producer CRUD, KPIs, strict enum typing and native share invite |  | 06/11/2026 |
| Fruitlogix-Multiplatform | main | 74daf66610a810432d6785f7887336cb4a371eae | feat(PaymentManagement): Implement Payment Management Bounded Context and integrate navigation |  | 11/11/2026 |
| Fruitlogix-Multiplatform | develop | 3ed7d46ebfaf10aa31f3c2d85b93fccfa2753578 | feat(order-management): implement demo checkout and order history |  | 09/11/2026 |
| Fruitlogix-Multiplatform | develop | eac76f3288a24605d01a760e428ee9e9ca1654fc | chore: bootstrap Flutter multiplatform application |  | 09/11/2026 |
| Fruitlogix-website-v2 | develop | 6c7f1e21d53179ca2ec82ad3d3dbc04b26ceae93 | feat: initial commit - structure and styles for FruitLogix landing page |  | 26/10/2026 |


#### 4.2.2.5 Execution Evidence for Sprint Review

En esta sección se presentan evidencias de la ejecución de la nueva versión de la Landing Page desarrollada y actualizada durante el Sprint 2.

**Figura 1. Sección principal de la landing page (v2)**

<div align="center">
  <img src="../assets/landingPage_v2/Landing1.png">
</div>

**Figura 2. Sección de solución (v2)**

<div align="center">
  <img src="../assets/landingPage_v2/Landing2.png">
</div>

**Figura 3. Sección de funcionalidades (v2)**

<div align="center">
  <img src="../assets/landingPage_v2/Landing3.png">
</div>

**Figura 4. Sección de segmentos (v2)**

<div align="center">
  <img src="../assets/landingPage_v2/Landing4.png">
</div>

**Figura 5. Sección de campo (v2)**

<div align="center">
  <img src="../assets/landingPage_v2/Landing5.png">
</div>

**Figura 6. Sección lo que viene (v2)**

<div align="center">
  <img src="../assets/landingPage_v2/Landing6.png">
</div>

**Figura 7. Sección del equipo (v2)**

<div align="center">
  <img src="../assets/landingPage_v2/Landing7.png">
</div>

**Figura 8. Sección final y llamado a la acción (v2)**

<div align="center">
  <img src="../assets/landingPage_v2/Landing8.png">
</div>

#### 4.2.2.6 Services Documentation Evidence for Sprint Review

Durante el Sprint 2 se concretó la integración entre los clientes móviles y los servicios backend RESTful desplegados en la nube (Render), habilitando la sincronización en tiempo real de pedidos, gestión de lotes, inventario de cosecha y mensajería operativa entre productores y distribuidores.

Para garantizar la interoperabilidad entre la aplicación nativa en Android (`Fruitlogix-AppMobile`) y la primera versión multiplataforma en Flutter (`Fruitlogix-Multiplatform`), los endpoints implementados fueron documentados formalmente bajo el estándar **OpenAPI (Swagger)**, detallando los esquemas de petición/respuesta en formato JSON, códigos de estado HTTP y políticas de autenticación mediante tokens JWT.

- **URL de documentación interactiva (Swagger UI):** `https://rebootech-fruitlogix-api.onrender.com/swagger/index.html`

#### 4.2.2.7. Software Deployment Evidence for Sprint Review.

Para el Sprint 2, la estrategia de despliegue abarcó la actualización pública de la **Landing Page v2**, la generación de la nueva versión instalable de la **aplicación móvil nativa en Android (APK)** y la compilación de la primera versión ejecutable de la **aplicación multiplataforma en Flutter**.

### A. Despliegue de la Landing Page Web (v2)

El despliegue de la versión renovada de la Landing Page de FruitLogix se realizó mediante **GitHub Pages**, actualizando automáticamente el sitio web estático tras integrar las mejoras visuales y la sección multimedia *About the Team*.

- **Repositorio de código fuente:** GitHub (`Fruitlogix-website-v2`)
- **Plataforma de despliegue:** GitHub Pages
- **Tipo de aplicación:** Landing Page estática (HTML5, CSS3, JavaScript)
- **URL de acceso público:** [https://upc-rebootech.github.io/Fruitlogix-website-v2/](https://upc-rebootech.github.io/Fruitlogix-website-v2/)

#### Proceso de Despliegue Web:
1. **Actualización de Recursos y Estilos:** Se incorporaron los nuevos bloques visuales, optimización de textos de propuesta de valor y el reproductor incrustado del video de presentación del equipo.
2. **Integración en Rama Principal (`main`):** Tras validar el diseño responsive en escritorio y dispositivos móviles, se fusionaron los cambios en la rama `main`.
3. **Publicación Continua:** GitHub Pages ejecutó de manera automática la compilación y publicación de la nueva versión del sitio en producción.

### B. Despliegue y Distribución de las Aplicaciones Móviles (Android Nativo y Flutter Multiplataforma)

Para los clientes móviles de FruitLogix, se generaron los artefactos binarios ejecutables correspondientes tanto a la aplicación nativa para productores y distribuidores como a la primera versión multiplataforma para clientes comerciales.

- **Repositorios de código fuente:** GitHub (`Fruitlogix-AppMobile` y `Fruitlogix-Multiplatform`)
- **Plataforma / Entorno de ejecución:** Android 8.0+ (API Level 26+) / Multiplataforma Dart & Flutter
- **Tecnologías:** Kotlin / Jetpack Compose y Flutter SDK
- **Mecanismo de distribución:** Compilación de paquetes instalables vinculados a los botones de descarga del sitio web.
- **URLs de acceso público:**
  - App Nativa (Productor/Distribuidor): [https://github.com/UPC-RebooTech/Fruitlogix-AppMobile.git](https://github.com/UPC-RebooTech/Fruitlogix-AppMobile.git)
  - App Multiplataforma (Clientes): [https://github.com/UPC-RebooTech/Fruitlogix-Multiplatform.git](https://github.com/UPC-RebooTech/Fruitlogix-Multiplatform.git)

#### Proceso de Despliegue Móvil:
1. **Integración de Servicios y Compilación:** Se configuraron las URLs base de la API desplegada en Render y se ejecutó la compilación en Gradle (`./gradlew assembleDebug`) para Android nativo y `flutter build apk` para el cliente multiplataforma.
2. **Validación Funcional:** Se verificó la estabilidad de los flujos de aceptación de pedidos del productor, el canal de chat logístico y la navegación inicial del catálogo comercial en Flutter.
3. **Distribución:** Los ejecutables generados fueron puestos a disposición del equipo y usuarios entrevistados para las pruebas de validación del Sprint Review.

#### 4.2.2.8. Team Collaboration Insights during Sprint

Para el desarrollo de este segundo sprint, todos los integrantes del equipo mantuvieron una participación activa y constante en los distintos repositorios del ecosistema FruitLogix. A continuación, se presentan las métricas de contribución e *insights* de colaboración del equipo en GitHub durante esta iteración.

<p align="left">
  <img src="../assets/insights/Team_Collaboration_Insights_Sprint2.png">
</p>