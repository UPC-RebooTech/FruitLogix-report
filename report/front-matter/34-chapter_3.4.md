## 3.4. Mobile Applications UX/UI Design

La propuesta de UX/UI de **FruitLogix** organiza la experiencia móvil en tres segmentos: **Distribuidores**, **Productores** y **Clientes Comerciales**. Para cada segmento se documentan las pantallas, su estructura de navegación, las decisiones de interacción y los recorridos vinculados con los objetivos del usuario (*user goals*). Esta separación permite representar las necesidades específicas de la operación logística, la gestión de producción y la compra comercial sin confundir sus responsabilidades.

Los entregables están articulados progresivamente: **wireframes** para definir distribución y jerarquía, **wireflows** para describir rutas con pantallas de baja fidelidad, **mock-ups** para desarrollar la propuesta visual, **user flows** para documentar recorridos sobre pantallas finales y **prototyping** para demostrar la navegación. Se elaboraron pantallas en **Figma** y diagramas de flujo en **Lucidchart**, conforme a las herramientas establecidas para el proyecto.

Se distingue el alcance de las evidencias: Distribuidores y Productores cuentan con referencias verificadas del aplicativo Android en Kotlin/Jetpack Compose; las pantallas y flujos de Clientes Comerciales corresponden al diseño de experiencia y a una propuesta/demostración funcional parcial. Las interacciones no verificadas en una aplicación desplegada se presentan como **propuestas de diseño**, no como funcionalidades productivas terminadas. Las capturas pendientes serán incorporadas por el equipo desde los archivos finales de diseño.

### 3.4.1. Mobile Applications Wireframes

Los wireframes describen la estructura de información y los elementos interactivos sin depender de los detalles de color, tipografía o ilustración. Se emplean para validar la ubicación de cabeceras, menús, filtros, tarjetas, formularios, llamados a la acción y estados de respuesta. La organización se orienta a reducir la carga cognitiva, mantener consistencia entre vistas y facilitar la comprensión de acciones y resultados.

#### 3.4.1.1. Distribuidores

Para el segmento de Distribuidores, los wireframes priorizan la supervisión de pedidos, despachos, facturación, recursos, productores vinculados, calidad e IoT. Las pantallas contemplan **Home Dashboard**, **Order Management**, **Fleet Control Center**, **Invoices & Billing**, **Drivers & Vehicles**, **Producer Network**, **Quality Control**, **Sensors & Alerts** y **Profile**. Se consideran asimismo vistas de detalle, formularios y estados auxiliares como creación y edición de pedidos, confirmación de eliminación, escaneo de recepción, detalle de despacho, rechazo de lotes, inspección en campo, reporte de incidencias y edición de umbrales.

La navegación principal permite localizar rápidamente los contextos operativos, mientras que los formularios mantienen secuencias de entrada claras y estados de validación asociados a las tareas críticas. Las pantallas de error, ausencia de datos y confirmación complementan la ruta principal y evitan representar únicamente el escenario exitoso.

![Mobile Applications Wireframes – Distributors](../assets/figma_files/mobile-wireframes-distributors.png)

**Figure 1. Mobile Applications Wireframes – Distributors.**

#### 3.4.1.2. Productores

Los wireframes para Productores se centran en **Home**, **Orders**, **Stock/Harvests**, **Inspection**, **Recojo en Fundo** y **Payouts**. Esta arquitectura responde a tareas de consulta de pedidos comerciales, aceptación de solicitudes, registro de cosechas, revisión de inventario, inspección de calidad, seguimiento del recojo y consulta de liquidaciones.

La estructura de cada pantalla comunica el estado de la operación y la siguiente acción disponible. Se incorporan representaciones de carga fallida, formularios incompletos, pedidos sin coincidencias, lotes rechazados o pendientes de reinspección, y jornadas sin unidades de recojo asignadas; estos estados permiten comprobar la continuidad del recorrido ante contingencias.

![Mobile Applications Wireframes – Producers](../assets/figma_files/mobile-wireframes-producers.png)

**Figure 2. Mobile Applications Wireframes – Producers.**

#### 3.4.1.3. Clientes Comerciales

Los wireframes de Clientes Comerciales presentan una experiencia enfocada en la compra y consulta: **Catalog**, **Cart**, **Orders**, **Order Detail**, **Track shipment**, **Payments** y **Profile**. El recorrido comienza con la exploración de productos, continúa con la selección de cantidades y el registro de un pedido, y se extiende a la consulta de órdenes, seguimiento, pagos y actualización del perfil.

Se priorizan las decisiones visibles del usuario, como filtrar el catálogo, revisar cantidades, completar datos de entrega o regresar cuando una búsqueda no ofrece resultados. Las vistas de seguimiento y pagos, así como determinados detalles, se consideran propuestas de experiencia y no evidencias de integración backend completa.

![Mobile Applications Wireframes – Commercial Clients](../assets/figma_files/mobile-wireframes-clients.png)

**Figure 3. Mobile Applications Wireframes – Commercial Clients.**

Los wireframes de los tres segmentos permiten evaluar la **arquitectura de información** antes de aplicar el sistema visual final. Sus estructuras facilitan el reconocimiento de las tareas más frecuentes, el acceso a las funciones principales y la recuperación frente a errores de interacción.

### 3.4.2. Mobile Applications Wireflow Diagrams

Los **wireflow diagrams** combinan los wireframes con acciones y transiciones para explicar cómo se alcanza cada *user goal*. Cada recorrido indica la pantalla inicial, el paso ejecutado por el usuario, las condiciones de decisión y la respuesta esperada de la interfaz. Cuando existe una ruta alternativa, se documenta su causa y la acción de recuperación. El cambio de estado debe visualizarse mediante una nueva pantalla o un estado diferenciado del wireframe; no solo mediante una flecha.

**Lucidchart – Wireflow Diagrams:** https://lucid.app/lucidchart/211bd6fa-755e-487a-94a1-77985f5b797c/edit?viewport_loc=-11429%2C-1062%2C26273%2C15138%2C0_0&invitationId=inv_4b89e1bb-dad2-482f-8756-b2942f168d42

#### 3.4.2.1. Distribuidores

Los wireflows del distribuidor describen el ciclo operativo del pedido y los procesos de apoyo a distribución y calidad. Se incluyen las condiciones de datos inválidos, recursos no habilitados, ausencia de información y alertas. La siguiente relación resume el **user goal** y las dos rutas que debe poder identificarse en cada diagrama.

| ID | User goal | Happy path | Unhappy path / recuperación |
|---|---|---|---|
| **D01** | Register commercial order | Orders → Create Order → ingresar producto, cantidad y fecha → registrar | Producto, cantidad o fecha inválidos: se muestran errores, se corrigen los campos y se reintenta. |
| **D02** | Edit commercial order | Orders → seleccionar pedido editable → Edit Order → guardar cambios | Pedido no editable o entradas inválidas: no se confirma la edición; revisar el estado y corregir. |
| **D03** | Delete commercial order | Orders → seleccionar pedido → solicitar eliminación → confirmar | Ventana de eliminación vencida (WINDOW_EXPIRED) o pedido no encontrado (NOT_FOUND): informar y no eliminar. |
| **D04** | Review order history | Orders → History → consultar o filtrar pedidos históricos | Búsqueda sin coincidencias: limpiar o modificar filtros. |
| **D05** | Scan lot reception | Orders → Scan Reception → escanear e identificar lote → validar recepción | Código incorrecto o lectura no válida: volver a escanear; contemplar permiso de cámara. |
| **D06** | Monitor dispatch and cold-chain risk | Fleet → Dispatch Detail → consultar ETA, temperatura y telemetría | Fallo de carga o alerta térmica: mostrar estado de error/alerta y revisar el despacho. |
| **D07** | Review invoices and billing | Invoices → filtrar facturas → abrir Invoice Detail → consultar estado e importe | Sin facturas o filtros sin coincidencias: ajustar criterios y consultar nuevamente. |
| **D08** | Assess driver and vehicle availability | Drivers & Vehicles → revisar habilitación → seleccionar recurso operativo | Conductor con licencia vencida o recurso no disponible: elegir otra opción. |
| **D09** | Invite or link producer | Producer Network → seleccionar invitación → generar o compartir vínculo | Compartir cancelado o información inválida: permanecer en el flujo y corregir/reintentar. |
| **D10** | Validate lot quality | Quality Control → seleccionar lote → revisar criterios → aprobar | Lote no conforme: ingresar motivo en Reject Dialog y confirmar rechazo. |
| **D11** | Register field inspection offline | Quality → inspección de campo → ingresar lote, temperatura y humedad → guardar localmente | Datos incompletos o temperatura fuera del rango admitido: corregir antes de guardar. |
| **D12** | Report incident with voice note | Quality → Incidents → registrar código, descripción y audio → enviar/registrar | Falta código, descripción o nota de voz: completar y volver a registrar. |
| **D13** | Review product losses | Quality → Mermas → seleccionar periodo → consultar indicadores | Periodo sin registros: mostrar estado vacío y cambiar el periodo. |
| **D14** | Adjust IoT thresholds | Sensors & Alerts → seleccionar umbral → editar y guardar | Rangos de umbral inválidos: indicar error y solicitar nuevos valores. |

![Mobile Applications Wireflow Diagrams – Distributors](../assets/figma_files/mobile-wireflows-distributors.png)

**Figure 4. Mobile Applications Wireflow Diagrams – Distributors.**

#### 3.4.2.2. Productores

En el segmento Productores, los recorridos parten del tablero, los pedidos recibidos o las secciones de inventario, inspección y pagos. Las decisiones describen cuándo se puede completar una operación y cuándo corresponde corregir datos, cambiar filtros o volver a intentar una carga.

| ID | User goal | Happy path | Unhappy path / recuperación |
|---|---|---|---|
| **P01** | Review producer dashboard | Home → cargar dashboard → consultar resumen y tareas | Error de carga: mostrar ErrorState y permitir Reintentar. |
| **P02** | Accept commercial order | Orders → seleccionar pedido pendiente → confirmar aceptación | Cancelación del diálogo: el pedido conserva su estado previo. |
| **P03** | Find and filter orders | Orders → seleccionar filtro/búsqueda → abrir pedido | Sin coincidencias, pestaña vacía o carga fallida: cambiar filtro o reintentar. |
| **P04** | Register harvest | Stock/Harvests → Register Harvest → completar lote y cantidad → guardar | Datos requeridos o cantidad inválidos: corregir formulario. |
| **P05** | Inspect harvest quality | Inspection → ingresar mediciones → Review report | Temperatura inferior a 5 °C o superior a 8 °C: mostrar error y deshabilitar revisión. |
| **P06** | Reinspect rejected lot | Inspection → abrir lote rechazado → realizar nueva revisión | Estado RE-INSPECTION REQUIRED: revisar y corregir mediciones antes de continuar. |
| **P07** | Consult stock and inventory | Stock → Inventory → elegir producto → Stock Detail | Inventario vacío o sin coincidencias: volver al listado o revisar criterios. |
| **P08** | Track pickup at farm | Recojo en Fundo → consultar unidad asignada, placa y ETA | Sin unidad asignada para hoy: informar ausencia de recojo programado. |
| **P09** | Review payouts | Payouts → filtrar por estado → consultar liquidaciones | Sin registros para el filtro: ajustar estados de búsqueda. |

![Mobile Applications Wireflow Diagrams – Producers](../assets/figma_files/mobile-wireflows-producers.png)

**Figure 5. Mobile Applications Wireflow Diagrams – Producers.**

#### 3.4.2.3. Clientes Comerciales

Los seis wireflows de Clientes Comerciales describen las metas prioritarias de exploración, compra, consulta y gestión de cuenta. Los diagramas muestran el recorrido esperado y la alternativa ante validaciones incompletas o información aún no disponible. Los escenarios de seguimiento y pagos son propuestas de interacción para la evolución del producto.

| ID | User goal | Happy path | Unhappy path / recuperación |
|---|---|---|---|
| **C-UF01** | Explore product catalog | Catalog → revisar frutas y filtros → seleccionar cantidades → carrito | Sin productos coincidentes o selección válida: ajustar filtros y volver a Catalog. |
| **C-UF02** | Place an order | Cart → revisar contenido → dirección y fecha → guardar pedido | Campos obligatorios incompletos: corregir dirección/fecha y volver a guardar. |
| **C-UF03** | Review my orders | Orders → seleccionar pedido de la sesión → revisar información | No existen pedidos: regresar al catálogo; el detalle ampliado es parte de la propuesta. |
| **C-UF04** | Track shipment | Orders → Order Detail → Track shipment → revisar ETA y estado | Seguimiento aún no asignado: informar disponibilidad y volver al pedido. |
| **C-UF05** | Review payments | Payments → filtrar movimientos → consultar importe y estado | Sin movimientos o filtros sin coincidencias: cambiar el filtro. |
| **C-UF06** | Update commercial profile | Profile → editar datos de contacto → guardar | Nombre, correo o teléfono inválidos: corregir y reintentar. |

![Mobile Applications Wireflow Diagrams – Commercial Clients](../assets/figma_files/mobile-wireflows-clients.png)

**Figure 6. Mobile Applications Wireflow Diagrams – Commercial Clients.**

Los flujos se relacionan con los objetivos del usuario y permiten contrastar la secuencia de tareas antes de aplicar mock-ups. Las rutas alternativas se consideran parte del diseño y no deben interpretarse automáticamente como pruebas de ejecución o implementación en producción.

### 3.4.3. Mobile Applications Mock-ups

Los **mock-ups** representan las interfaces con mayor fidelidad visual. Se emplea una identidad consistente con FruitLogix, basada en **tonos verdes, fondos claros, tarjetas de información, jerarquías tipográficas y acciones diferenciadas**. Se preservan los nombres funcionales de las secciones en inglés y se utilizan estados visibles para comunicar situaciones como pedidos pendientes, recursos disponibles, incidencias, alertas y registros sin resultados.

El diseño responde a principios de **consistencia, visibilidad del estado del sistema, prevención de errores y reconocimiento antes que recuerdo**. Para favorecer un uso inclusivo, se priorizan textos legibles, agrupación semántica, objetivos táctiles comprensibles y señales de estado que no dependan exclusivamente del color. Los formularios se estructuran verticalmente para reducir omisiones y presentar mensajes de validación cerca de su origen.

#### 3.4.3.1. Distribuidores

Los mock-ups de Distribuidores materializan las vistas de pedidos, seguimiento de flota, facturación, conductores y vehículos, vínculo con productores, calidad y sensores. El **Home Dashboard** sintetiza información operativa, mientras que las tarjetas, etiquetas de estado, indicadores de temperatura y listados facilitan la lectura rápida de datos de control. Las pantallas de creación, edición y consulta muestran acciones principales consistentes; los estados de error y confirmación informan el resultado de cada operación.

La separación visual entre información, acciones y advertencias evita que una tarea crítica, como rechazar un lote o atender una alerta térmica, se confunda con una consulta de rutina.

<!-- PENDIENTE: subir captura a report/assets/figma_files/mobile-mockups-distributors.png y activar la línea siguiente. -->
![Mobile Applications Mock-ups – Distributors](../assets/figma_files/mobile-mockups-distributors.png)

**Figure 7. Mobile Applications Mock-ups – Distributors.**

#### 3.4.3.2. Productores

Los mock-ups de Productores presentan resúmenes de actividad, pedidos recibidos, cosechas, inventario, inspección, recolección y liquidaciones. En **Orders** se distinguen solicitudes pendientes y estados de atención; en **Stock/Harvests** se ordena el registro y consulta de productos; en **Inspection** se resaltan mediciones, resultado y necesidad de reinspección.

Las interfaces de recojo comunican la asignación de unidad y la información de llegada cuando está disponible. Los estados vacíos y de error se integran con el mismo lenguaje visual, facilitando el retorno a una acción útil.

<!-- PENDIENTE: subir captura a report/assets/figma_files/mobile-mockups-producers.png y activar la línea siguiente. -->
![Mobile Applications Mock-ups – Producers](../assets/figma_files/mobile-mockups-producers.png)

**Figure 8. Mobile Applications Mock-ups – Producers.**

#### 3.4.3.3. Clientes Comerciales

Los mock-ups de Clientes Comerciales presentan el catálogo de frutas, la selección de cantidades, el carrito, el formulario de pedido, la lista y detalle de órdenes, el seguimiento de despacho, los pagos y el perfil. La jerarquía visual acompaña una secuencia comprensible: **descubrir → seleccionar → confirmar → consultar**. Las tarjetas de producto destacan información relevante para decidir la compra; el carrito resume la selección, y el formulario organiza los campos necesarios para registrar la solicitud.

En las vistas posteriores a la compra, la lectura de estados y datos de entrega tiene prioridad frente a elementos secundarios. Las pantallas relacionadas con pagos y seguimiento representan el diseño objetivo de la experiencia, sujeto a integración funcional futura cuando corresponda.

<!-- PENDIENTE: subir captura a report/assets/figma_files/mobile-mockups-clients.png y activar la línea siguiente. -->
![Mobile Applications Mock-ups – Commercial Clients](../assets/figma_files/mobile-mockups-clients.png)

**Figure 9. Mobile Applications Mock-ups – Commercial Clients.**

Los mock-ups constituyen la referencia visual para los User Flow Diagrams y el prototipo. La correspondencia entre la pantalla inicial, la acción y su estado siguiente ayuda a mantener coherencia entre las decisiones de navegación, el diseño visual y los recorridos documentados.

### 3.4.4. Mobile Applications User Flow Diagrams

Los **User Flow Diagrams** se derivan de los wireflows y utilizan **mock-ups finales**, en lugar de pantallas de baja fidelidad. Cada diagrama identifica el objetivo del usuario, la pantalla de origen, las acciones y las condiciones de decisión, con un **happy path** que llega al resultado esperado y un **unhappy path** que expone el error, la ausencia de información o la condición que impide continuar. Las conexiones permiten observar el retorno al flujo cuando el usuario corrige o modifica su acción.

**Lucidchart – User Flow Diagrams:** https://lucid.app/lucidchart/149ee5c9-81ed-4f36-9fc2-0a245272437d/edit?viewport_loc=-32147%2C3801%2C90357%2C43300%2C0_0&invitationId=inv_d90ccecb-2f67-4810-9512-c2f02fe53eba

#### 3.4.4.1. Distribuidores

Los User Flows del distribuidor visualizan las mismas metas y condiciones expuestas en la sección 3.4.2.1, ahora mediante las interfaces de alta fidelidad. Los recorridos relativos al pedido muestran el paso desde la lista hacia formularios, confirmaciones o estados de error. Los recorridos de logística, recursos, calidad y sensores explicitan cómo las decisiones cambian ante la disponibilidad de un conductor, el resultado de inspección o una alerta de temperatura.

**User goals documentados:**

- **D01 – Register commercial order:** Orders → Create Order → ingresar producto, cantidad y fecha → registrar. **Ruta alternativa:** producto, cantidad o fecha inválidos: se muestran errores, se corrigen los campos y se reintenta.
- **D02 – Edit commercial order:** Orders → seleccionar pedido editable → Edit Order → guardar cambios. **Ruta alternativa:** pedido no editable o entradas inválidas: no se confirma la edición; revisar el estado y corregir.
- **D03 – Delete commercial order:** Orders → seleccionar pedido → solicitar eliminación → confirmar. **Ruta alternativa:** ventana de eliminación vencida (WINDOW_EXPIRED) o pedido no encontrado (NOT_FOUND): informar y no eliminar.
- **D04 – Review order history:** Orders → History → consultar o filtrar pedidos históricos. **Ruta alternativa:** búsqueda sin coincidencias: limpiar o modificar filtros.
- **D05 – Scan lot reception:** Orders → Scan Reception → escanear e identificar lote → validar recepción. **Ruta alternativa:** código incorrecto o lectura no válida: volver a escanear; contemplar permiso de cámara.
- **D06 – Monitor dispatch and cold-chain risk:** Fleet → Dispatch Detail → consultar ETA, temperatura y telemetría. **Ruta alternativa:** fallo de carga o alerta térmica: mostrar estado de error/alerta y revisar el despacho.
- **D07 – Review invoices and billing:** Invoices → filtrar facturas → abrir Invoice Detail → consultar estado e importe. **Ruta alternativa:** sin facturas o filtros sin coincidencias: ajustar criterios y consultar nuevamente.
- **D08 – Assess driver and vehicle availability:** Drivers & Vehicles → revisar habilitación → seleccionar recurso operativo. **Ruta alternativa:** conductor con licencia vencida o recurso no disponible: elegir otra opción.
- **D09 – Invite or link producer:** Producer Network → seleccionar invitación → generar o compartir vínculo. **Ruta alternativa:** compartir cancelado o información inválida: permanecer en el flujo y corregir/reintentar.
- **D10 – Validate lot quality:** Quality Control → seleccionar lote → revisar criterios → aprobar. **Ruta alternativa:** lote no conforme: ingresar motivo en Reject Dialog y confirmar rechazo.
- **D11 – Register field inspection offline:** Quality → inspección de campo → ingresar lote, temperatura y humedad → guardar localmente. **Ruta alternativa:** datos incompletos o temperatura fuera del rango admitido: corregir antes de guardar.
- **D12 – Report incident with voice note:** Quality → Incidents → registrar código, descripción y audio → enviar/registrar. **Ruta alternativa:** falta código, descripción o nota de voz: completar y volver a registrar.
- **D13 – Review product losses:** Quality → Mermas → seleccionar periodo → consultar indicadores. **Ruta alternativa:** periodo sin registros: mostrar estado vacío y cambiar el periodo.
- **D14 – Adjust IoT thresholds:** Sensors & Alerts → seleccionar umbral → editar y guardar. **Ruta alternativa:** rangos de umbral inválidos: indicar error y solicitar nuevos valores.

![Mobile Applications User Flow Diagrams – Distributors](../assets/figma_files/mobile-userflows-distributors.png)

**Figure 10. Mobile Applications User Flow Diagrams – Distributors.**

#### 3.4.4.2. Productores

Los User Flows del productor emplean las pantallas finales para evidenciar las transiciones desde Home, Orders, Stock, Inspection, Recojo en Fundo y Payouts. Se enfatizan decisiones relevantes como la confirmación de aceptación del pedido, la validación del registro de cosecha y la habilitación de la revisión de calidad únicamente cuando las mediciones son admisibles.

**User goals documentados:**

- **P01 – Review producer dashboard:** Home → cargar dashboard → consultar resumen y tareas. **Ruta alternativa:** error de carga: mostrar ErrorState y permitir Reintentar.
- **P02 – Accept commercial order:** Orders → seleccionar pedido pendiente → confirmar aceptación. **Ruta alternativa:** cancelación del diálogo: el pedido conserva su estado previo.
- **P03 – Find and filter orders:** Orders → seleccionar filtro/búsqueda → abrir pedido. **Ruta alternativa:** sin coincidencias, pestaña vacía o carga fallida: cambiar filtro o reintentar.
- **P04 – Register harvest:** Stock/Harvests → Register Harvest → completar lote y cantidad → guardar. **Ruta alternativa:** datos requeridos o cantidad inválidos: corregir formulario.
- **P05 – Inspect harvest quality:** Inspection → ingresar mediciones → Review report. **Ruta alternativa:** temperatura inferior a 5 °C o superior a 8 °C: mostrar error y deshabilitar revisión.
- **P06 – Reinspect rejected lot:** Inspection → abrir lote rechazado → realizar nueva revisión. **Ruta alternativa:** estado RE-INSPECTION REQUIRED: revisar y corregir mediciones antes de continuar.
- **P07 – Consult stock and inventory:** Stock → Inventory → elegir producto → Stock Detail. **Ruta alternativa:** inventario vacío o sin coincidencias: volver al listado o revisar criterios.
- **P08 – Track pickup at farm:** Recojo en Fundo → consultar unidad asignada, placa y ETA. **Ruta alternativa:** sin unidad asignada para hoy: informar ausencia de recojo programado.
- **P09 – Review payouts:** Payouts → filtrar por estado → consultar liquidaciones. **Ruta alternativa:** sin registros para el filtro: ajustar estados de búsqueda.

![Mobile Applications User Flow Diagrams – Producers](../assets/figma_files/mobile-userflows-producers.png)

**Figure 11. Mobile Applications User Flow Diagrams – Producers.**

#### 3.4.4.3. Clientes Comerciales

Los User Flows de Clientes Comerciales se construyeron a partir de los mock-ups finales, con **seis recorridos** destinados a la compra y gestión de cuenta. La meta, acción, decisión y resultado se identifican en cada caso. En el happy path, el usuario alcanza su objetivo; en el unhappy path, se documenta el estado alternativo y una acción para corregir la situación o regresar a una pantalla anterior.

**User goals documentados:**

- **C-UF01 – Explore product catalog:** Catalog → revisar frutas y filtros → seleccionar cantidades → carrito. **Ruta alternativa:** sin productos coincidentes o selección válida: ajustar filtros y volver a Catalog.
- **C-UF02 – Place an order:** Cart → revisar contenido → dirección y fecha → guardar pedido. **Ruta alternativa:** campos obligatorios incompletos: corregir dirección/fecha y volver a guardar.
- **C-UF03 – Review my orders:** Orders → seleccionar pedido de la sesión → revisar información. **Ruta alternativa:** no existen pedidos: regresar al catálogo; el detalle ampliado es parte de la propuesta.
- **C-UF04 – Track shipment:** Orders → Order Detail → Track shipment → revisar ETA y estado. **Ruta alternativa:** seguimiento aún no asignado: informar disponibilidad y volver al pedido.
- **C-UF05 – Review payments:** Payments → filtrar movimientos → consultar importe y estado. **Ruta alternativa:** sin movimientos o filtros sin coincidencias: cambiar el filtro.
- **C-UF06 – Update commercial profile:** Profile → editar datos de contacto → guardar. **Ruta alternativa:** nombre, correo o teléfono inválidos: corregir y reintentar.

![Mobile Applications User Flow Diagrams – Commercial Clients](../assets/figma_files/mobile-userflows-clients.png)

**Figure 12. Mobile Applications User Flow Diagrams – Commercial Clients.**

La distinción entre escenarios permite evaluar la experiencia más allá de la secuencia ideal. En particular, para Clientes Comerciales los flujos de **Track shipment** y **Payments**, así como determinados estados de detalle, representan funcionalidades **propuestas**; la presencia de un mock-up en el diagrama no equivale a una implementación conectada a servicios reales.

### 3.4.5. Mobile Applications Prototyping

El prototipado conecta las vistas de alta fidelidad y simula la interacción entre pantallas para evaluar la continuidad de las tareas. Se mantiene correspondencia con la arquitectura de información de cada segmento: **acceso desde el menú principal, navegación hacia listas y detalles, acciones contextuales, formularios de registro y retorno a la pantalla de origen**. La propuesta busca mantener una ubicación predecible de las funciones y retroalimentación visible después de decisiones relevantes.

La simulación considera principios de navegación consistentes: mantener accesibles las funciones principales; utilizar acciones contextuales para evitar sobrecargar menús; diferenciar tareas de consulta de operaciones que modifican información; conservar el contexto al volver desde un detalle; y prever confirmaciones o validaciones antes de completar acciones sensibles. Los prototipos deben interpretarse como una **demostración UX/UI**, no como una validación de conectividad o persistencia de backend.

**Figma prototype:** https://www.figma.com/design/dk6coJvuEa9eGrT0lKQRv0/Fruitlogix-Mobile?node-id=109-3&t=8XPP5h9Cx4GX4pvo-1

**Prototype demonstration video:** https://upcedupe-my.sharepoint.com/:v:/g/personal/u20241b761_upc_edu_pe/IQCTfbOr7XE9SInob6f6PuoJAd0fQjEL4ct2U-pS4Gz6Spk?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D&e=KolrJv

El prototipo demuestra los recorridos principales de la aplicación y mantiene correspondencia con los Wireflow Diagrams y User Flow Diagrams definidos anteriormente.

