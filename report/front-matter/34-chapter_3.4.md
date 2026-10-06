## 3.4. Mobile Applications UX/UI Design

La propuesta UX/UI de la aplicación móvil FruitLogix fue diseñada para soportar las operaciones principales del distribuidor logístico desde un dispositivo Android. La solución prioriza una navegación simple, acceso rápido a los bounded contexts principales y una presentación visual consistente para tareas de monitoreo, pedidos, facturación, calidad, sensores, conductores y productores.

Las pantallas fueron construidas tomando como referencia la versión implementada de la aplicación móvil, de modo que los artefactos de diseño mantengan correspondencia con la interfaz desarrollada. Para los wireframes, mock-ups y prototipo se utilizó Figma; para los wireflows y user flows se utilizó Lucidchart.

### 3.4.1. Mobile Applications Wireframes

Los wireframes representan la estructura de las pantallas principales de FruitLogix antes de considerar el detalle visual final. Se mantuvo la jerarquía de información de la aplicación implementada, incluyendo encabezados, navegación inferior, tarjetas de información, formularios, filtros, estados y acciones principales.

La propuesta cubre las pantallas core de Home Dashboard, Order Management, Fleet Control Center, Invoices & Billing, Profile, Drivers & Vehicles, Producer Network, Quality Control y Sensors & Alerts. También se incluyeron estados auxiliares necesarios para representar interacciones relevantes, como Register New Order, Invoice Detail, Edit Profile, rechazo de lotes, Field Inspection y Report Incident.

![Mobile Applications Wireframes](../assets/figma_files/mobile-wireframes.png)

**Figure 1. Mobile Applications Wireframes for FruitLogix.**

Los wireframes fueron diseñados con baja fidelidad para priorizar la distribución del contenido, el flujo de navegación y la ubicación de controles antes de aplicar el sistema visual definitivo. Asimismo, las vistas consideran la navegación persistente de la aplicación mediante las secciones Home, Orders, Fleet, Invoices y More.

### 3.4.2. Mobile Applications Wireflow Diagrams

Los wireflows combinan los wireframes con los pasos de interacción requeridos para alcanzar cada User Goal. Cada flujo presenta el happy path y, cuando corresponde, un unhappy path asociado a una condición de validación, disponibilidad o estado operativo.

Link LucidChart Wireflow: https://lucid.app/lucidchart/211bd6fa-755e-487a-94a1-77985f5b797c/edit?viewport_loc=-11429%2C-1062%2C26273%2C15138%2C0_0&invitationId=inv_4b89e1bb-dad2-482f-8756-b2942f168d42

**Figure 2. Mobile Applications Wireflow Diagrams for FruitLogix.**

| ID | User Goal | Descripción del flujo |
|---|---|---|
| WF-UG01 | Register commercial order | El usuario accede a Orders, abre el formulario de registro y completa variedad, cantidad y fecha requerida. Si los datos son válidos, el pedido se registra; en caso contrario, se corrigen los campos antes de reintentar. |
| WF-UG02 | Monitor dispatch and cold-chain risk | El usuario accede al Fleet Control Center y revisa telemetría, temperatura, humedad y ETA. Si los valores son normales, continúa el monitoreo; ante una anomalía, revisa la alerta y toma una acción correctiva. |
| WF-UG03 | Review billing and invoice detail | El usuario accede a Invoices & Billing, selecciona una factura y revisa importe, tipo y estado. Si no encuentra resultados, ajusta o limpia los filtros y realiza una nueva búsqueda. |
| WF-UG04 | Assess driver availability | El usuario accede a Drivers & Vehicles y revisa disponibilidad, licencia y estado operativo. Si el conductor no está habilitado, selecciona otro recurso disponible. |
| WF-UG05 | Invite producer | El usuario accede a Producer Network, abre el formulario de invitación y registra los datos del productor. Si la información es válida, envía la invitación; de lo contrario, corrige los campos requeridos. |
| WF-UG06 | Validate lot quality | El usuario revisa un lote en Quality Control y evalúa sus condiciones. Si cumple los criterios, lo aprueba; si no los cumple, registra el motivo de rechazo y confirma la operación. |
| WF-UG07 | Report incident with voice note | El usuario registra código de lote, descripción y nota de voz. Con la información completa puede registrar la incidencia; si faltan datos o audio, permanece en el formulario hasta completarlos. |
| WF-UG08 | Monitor IoT alerts and device state | El usuario revisa alertas telemáticas y dispositivos IoT. Si el dispositivo funciona normalmente, continúa el monitoreo o calibración; ante desconexión, batería baja o alerta crítica, revisa el dispositivo afectado. |
| WF-UG09 | Update profile information | El usuario accede a Profile, selecciona Edit Profile y modifica sus datos. Si la información es válida, guarda los cambios; de lo contrario, corrige los campos antes de volver a validar. |
| WF-UG10 | Register field inspection offline | El usuario accede a la inspección en campo y registra lote, producto, temperatura y humedad. Si la información es válida, la inspección se almacena localmente y queda preparada para sincronización; si no, se corrigen los datos. |

### 3.4.3. Mobile Applications Mock-ups

Los mock-ups presentan la propuesta visual de alta fidelidad alineada con la aplicación Android desarrollada. Se aplicó una identidad basada en tonos verde oscuro, verde lima y fondos claros, manteniendo un contraste alto entre información operativa, estados y acciones.

![Mobile Applications Mock-ups](../assets/figma_files/mobile-mockups.png)

**Figure 3. Mobile Applications Mock-ups for FruitLogix.**

El diseño utiliza tarjetas para agrupar información relacionada, botones de acción claramente diferenciados, estados visuales para condiciones como Pending, On Route, Available, Overdue o Alert, y una barra de navegación inferior persistente. En los bounded contexts de Fleet, Quality Control y Sensors & Alerts se utilizan indicadores visuales que permiten reconocer rápidamente situaciones normales, preventivas o críticas.

Los formularios mantienen una disposición vertical y campos de entrada amplios para facilitar su uso en dispositivos móviles. Los estados auxiliares, como diálogos de rechazo, edición de perfil, registro de pedidos e invitación de productores, conservan el mismo sistema visual y jerarquía de información.

### 3.4.4. Mobile Applications User Flow Diagrams

Los User Flow Diagrams se derivan directamente de los wireflows y utilizan los mock-ups finales para mostrar la experiencia esperada del usuario. Cada User Flow representa el recorrido necesario para alcanzar un objetivo, incluyendo tanto el happy path como las rutas alternativas o unhappy paths.

Link LucidChart Wireflow: [https://lucid.app/lucidchart/211bd6fa-755e-487a-94a1-77985f5b797c/edit?viewport_loc=-11429%2C-1062%2C26273%2C15138%2C0_0&invitationId=inv_4b89e1bb-dad2-482f-8756-b2942f168d42](https://lucid.app/lucidchart/149ee5c9-81ed-4f36-9fc2-0a245272437d/edit?viewport_loc=-9290%2C-6134%2C23048%2C13280%2C0_0&invitationId=inv_d90ccecb-2f67-4810-9512-c2f02fe53eba)

**Figure 4. Mobile Applications User Flow Diagrams for FruitLogix.**

- **UF-UG01 – Register commercial order:** registro de un nuevo pedido y corrección de datos inválidos.
- **UF-UG02 – Monitor dispatch and cold-chain risk:** monitoreo de despacho y atención de riesgos de cadena de frío.
- **UF-UG03 – Review billing and invoice detail:** consulta de facturación, detalle de factura y manejo de búsquedas sin resultados.
- **UF-UG04 – Assess driver availability:** evaluación de disponibilidad y habilitación operativa de conductores.
- **UF-UG05 – Invite producer:** registro y envío de invitaciones a productores.
- **UF-UG06 – Validate lot quality:** aprobación o rechazo de lotes según criterios de calidad.
- **UF-UG07 – Report incident with voice note:** registro de incidencias complementado con una nota de voz.
- **UF-UG08 – Monitor IoT alerts and device state:** revisión de alertas IoT, conectividad y estado de dispositivos.
- **UF-UG09 – Update profile information:** edición y validación de información de perfil.
- **UF-UG10 – Register field inspection offline:** registro de inspecciones en campo con almacenamiento local para posterior sincronización.

En todos los casos, el happy path representa la secuencia esperada cuando se cumplen las condiciones necesarias, mientras que el unhappy path muestra cómo la interfaz responde ante información incompleta, estados no habilitados, ausencia de resultados o condiciones operativas anómalas.

### 3.4.5. Mobile Applications Prototyping

El prototipo móvil integra las pantallas de alta fidelidad y permite representar la navegación entre los principales bounded contexts y estados de interacción. La propuesta prioriza un sistema de navegación persistente mediante la barra inferior y un menú More para acceder a funciones complementarias como Profile, Drivers, Producers, Quality y Sensors.

![Mobile Applications Prototype](../assets/figma_files/mobile-prototype.png)

**Figure 5. Mobile Applications Prototype screens for FruitLogix.**

Los principales criterios de interacción considerados son los siguientes:

- Mantener accesibles las funciones core desde la navegación inferior.
- Utilizar More para funcionalidades complementarias sin sobrecargar la navegación principal.
- Mantener consistencia entre estados normales, preventivos y críticos.
- Mostrar acciones contextuales dentro de cada bounded context.
- Utilizar formularios verticales y acciones principales claramente identificables.
- Conservar el contexto del usuario al regresar desde pantallas de detalle o edición.
- Representar de forma explícita las validaciones y rutas alternativas definidas en los User Flows.

**Figma prototype:** https://www.figma.com/design/dk6coJvuEa9eGrT0lKQRv0/Fruitlogix-Mobile?node-id=109-3&t=8XPP5h9Cx4GX4pvo-1

**Prototype demonstration video:** https://upcedupe-my.sharepoint.com/:v:/g/personal/u20241b761_upc_edu_pe/IQCTfbOr7XE9SInob6f6PuoJAd0fQjEL4ct2U-pS4Gz6Spk?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D&e=KolrJv

El prototipo demuestra los recorridos principales de la aplicación y mantiene correspondencia con los Wireflow Diagrams y User Flow Diagrams definidos anteriormente.
