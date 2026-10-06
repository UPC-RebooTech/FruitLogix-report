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
| Sum of Story Points | ## |

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
| Cabrera Novoa, Leonardo Moisés | Cmarin2802 | L | C | C | C |
| Pinedo Sanchez, Sebastián Martín | CamilaaAlizee | L | C | C | C |

#### 4.2.1.3 Sprint Backlog 1

El objetivo del presente Sprint fue el diseño y desarrollo de la landing page del sistema Aquanetix, enfocándose en la comunicación efectiva de la propuesta de valor, la presentación de funcionalidades clave y la facilitación del contacto con potenciales usuarios.

Durante este Sprint, el equipo trabajó de manera colaborativa en la construcción de las diferentes secciones de la landing page, asegurando una experiencia de usuario clara, intuitiva y alineada con los objetivos del sistema.

<div align="center">
  <img src="../assets/Jira/Sprint1_1.png">
  <img src="../assets/Jira/Sprint1_2.png">
  <img src="../assets/Jira/Sprint1_3.png">
  <img src="../assets/Jira/Sprint1_4.png">
</div>

Enlace a la herramienta utilizada: ...

A continuación, se detallan las User Stories priorizadas y las tareas asociadas:

| US Id | Title | Task Id | Task Title | Description | Estimation (Hours) | Assigned To | Status |
|------|------|--------|------------|------------|-------------------|-------------|--------|
| US-35 | Visualización de información de producto | T-01 | Creación de la Landing page | Crear la página web del producto | 6 | Sebastián Pinedo | Done |


#### 5.2.1.4 Development Evidence for Sprint Review

| Repository | Branch | Commit Ids | Commit Message | Commit Message Body | Committed on (Date) |
|------------|--------|-----------|----------------|---------------------|---------------------|
| aquanetix-repo | develop | 4f01889ae5953aba422050a86048518fc2e68577 | docs: add epics for requirements |  | 18/04/2026 |

#### 4.2.1.5 Execution Evidence for Sprint Review

En esta sección se presentan evidencias de la ejecución de la landing page desarrollada durante el Sprint.

**Figura 1. Sección principal de la landing page**

<div align="center">
  <img src="../assets/LandingPage/Landing1.jpeg">
</div>
La figura muestra la sección principal de la landing page, donde se presenta la propuesta de valor del sistema Aquanetix junto con un llamado a la acción dirigido al usuario.


**Figura 2. Sección informativa de la landing page**

<div align="center">
  <img src="../assets/LandingPage/Landing2.jpeg">
</div>

En esta sección se describe el problema abordado y la solución propuesta por el sistema, permitiendo al usuario comprender el propósito y beneficios del servicio.

**Figura 3. Sección de funcionalidades**

<div align="center">
  <img src="../assets/LandingPage/Landing3.jpeg">
</div>

La figura muestra las principales funcionalidades del sistema, destacando las capacidades de monitoreo, gestión de alertas y análisis de datos.

**Figura 4. Sección final y llamado a la acción**

<div align="center">
  <img src="../assets/LandingPage/Landing4.jpeg">
</div>

En esta sección final se incluye un llamado a la acción que invita al usuario a interactuar con el sistema, junto con información adicional relevante.

Tambien se procedió a grabar un video demostrando a detalle la funcionalidad de la Landing Page de nuestra aplicación: https://shorturl.at/L8IDq

#### 4.2.1.6 Services Documentation Evidence for Sprint Review

...

#### 4.2.1.7. Software Deployment Evidence for Sprint Review.

...

#### 4.2.1.8. Team Collaboration Insights during Sprint

Para el desarrollo de este primer sprint, todos los miembros del equipo desarrollaron y colaboraron de manera activa y continua. De tal modo, se muestra como evidencia los insights de cada miembro del equipo.
<p align = "left">
   <img src="../assets/insights/Team Collaboration Insights.jpg">
</p>
