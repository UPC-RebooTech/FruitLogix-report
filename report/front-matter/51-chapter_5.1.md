## Capítulo V: Product Implementation, Validation & Deployment
### 5.1. Software Configuration Management
#### 5.1.1. Software Development Environment Configuration
Con el objetivo de garantizar un desarrollo fluido, estandarizado y consistente entre todos los miembros del equipo **RebooTech**, se ha definido el siguiente entorno de desarrollo para el ecosistema de la aplicación móvil **FruitLogix**:

| Actividad | Producto | Propósito / Uso |
| :--- | :--- | :--- |
| **Project Management** | Trello | Gestión del Product Backlog, planificación de Sprints y seguimiento de tareas. |
| **Requirements Management** | UXPressia | Elaboración de artefactos de descubrimiento (User Personas, Empathy Maps, Journey Maps) para la definición de requisitos. |
| **UX/UI Design** | Figma | Diseño de la guía de estilo, prototipos de baja fidelidad (wireframes) y alta fidelidad (mockups) basados en **Material Design 3**. |
| **User Flows & Wireflows** | Lucidchart | Elaboración de Wireflows y flujos de navegación de la aplicación móvil (User Flows). |
| **Class Diagrams & Data Base Design** | PlantUML | Elaboración de diagramas de clases, diagramas de componentes y diseño de arquitectura de datos. |
| **Software Development (Mobile App)** | Android Studio | IDE oficial para el desarrollo nativo en **Kotlin** utilizando **Jetpack Compose** como framework declarativo de interfaz de usuario. |
| **Software Development (Backend Services)** | JetBrains Rider / VS Code | IDE para el desarrollo de Web Services bajo arquitectura RESTful utilizando **ASP.NET Core (C#)** consumidos por la aplicación móvil. |
| **Build & Dependency Management** | Gradle | Sistema de automatización de compilación y gestión de dependencias para el proyecto Android. |
| **Version Control** | GitHub | Alojamiento de repositorios y gestión de versiones aplicando **GitFlow** y **Conventional Commits**. |
| **Documentation** | Markdown | Documentación técnica del reporte del proyecto y manuales de arquitectura. |

#### 5.1.2. Source Code Management

El código fuente del proyecto se gestionará utilizando **Git** como sistema de control de versiones y **GitHub** como plataforma de alojamiento, bajo una organización pública. Se adoptará un enfoque estructurado que favorezca la colaboración, la modularidad y el despliegue continuo mediante repositorios independientes para la aplicación móvil y sus servicios de soporte.

#### Estrategia de Ramas (GitFlow)

Se implementará un flujo de trabajo basado en **GitFlow** con el objetivo de garantizar la estabilidad y trazabilidad del desarrollo:

- **`main`**: Rama principal que contiene únicamente código estable, probado y listo para la generación de ejecutable final de producción (APK / AAB). Cada versión liberada estará debidamente etiquetada con un versión semántica (ej. `v1.0.0`).
- **`develop`**: Rama de integración continua donde se consolidan los avances del desarrollo de la app móvil antes de la fase de testing y preparación de release.
- **`feature/[nombre]`**: Ramas temporales creadas a partir de `develop` para el desarrollo de nuevas pantallas, módulos o User Stories (ej. `feature/order-list-ui`, `feature/firebase-auth`). Una vez finalizadas y probadas, se integran nuevamente a `develop` mediante un Pull Request (PR) aprobado por el líder técnico.
- **`hotfix/[nombre]`**: Ramas destinadas a la corrección de errores críticos detectados en producción (`main`), que requieren una solución o parche inmediato.

#### Convención de Commits (Conventional Commits)

Para mantener un historial claro, consistente y facilitar la trazabilidad de los cambios en el código de la aplicación, todos los commits deberán seguir el estándar de **Conventional Commits**:

#### Tipos permitidos
- **`feat`**: Nueva funcionalidad o pantalla de la aplicación  
  *(ej. `feat(orders): implement Jetpack Compose UI for order detail screen`)*
- **`fix`**: Corrección de errores en la lógica o la interfaz  
  *(ej. `fix(auth): resolve token expiration crash on background resume`)*
- **`docs`**: Cambios en la documentación o diagramas  
  *(ej. `docs(architecture): update MVVM data flow diagram`)*
- **`style`**: Cambios de formato, indentación o limpieza que no afectan la lógica del código  
  *(ej. `style(ui): reformat code layout and compose preview modifiers`)*
- **`refactor`**: Reestructuración de código sin alterar el comportamiento de la app  
  *(ej. `refactor(repository): migrate local storage to Room database`)*

#### 5.1.3. Source Code Style Guide & Conventions

Para garantizar la legibilidad, mantenibilidad y calidad del código en todo el equipo de desarrollo de la aplicación móvil **FruitLogix**, se adoptan las siguientes guías de estilo:

#### Para la Aplicación Móvil (Android / Kotlin & Jetpack Compose)

Se seguirán las guías oficiales de estilo de Kotlin y las buenas prácticas de arquitectura para Android sugeridas por Google (MVVM + Unidirectional Data Flow).

#### Nomenclatura
- **Funciones Composable**: `PascalCase` y sustantivos (ej. `@Composable fun OrderCard()`, `@Composable fun HomeScreen()`).
- **Clases y ViewModels**: `PascalCase` (ej. `OrderViewModel`, `TaskRepository`, `UserEntity`).
- **Funciones estándar y variables**: `camelCase` (ej. `fetchOrders()`, `uiState`, `isOrderCompleted`).
- **Paquetes**: Todo en minúsculas sin guiones ni guiones bajos (ej. `pe.edu.upc.fruitlogix.ui.orders`).
- **Recursos XML (Drawables, Strings, Colors)**: `snake_case` (ej. `ic_shopping_cart.xml`, `app_name`).

#### Estructura del Proyecto
- **Separación de capas (Clean Architecture / MVVM)**:
  - `ui/`: Contiene los Composables (Views), ViewModels y estados de interfaz (`UiState`).
  - `data/`: Contiene los Repositorios, Fuentes de Datos (Remote/Local APIs) y Modelos de datos (DTOs).
  - `domain/`: Contiene los Casos de Uso (Use Cases) y Entidades del negocio.
- **Uso de Estado Unidireccional (UDF)**: Modificación del estado únicamente a través de ViewModels exponiendo `StateFlow` o `mutableStateOf`.

#### Formateo
- Uso de la herramienta **ktlint** o el formateador integrado de Android Studio para mantener 4 espacios de indentación.
- Evitar funciones Composable masivas; descomponer componentes en sub-composables reutilizables.

### Para el Backend / Servicios RESTful (ASP.NET Core / C#)

Se adoptarán las convenciones estándar de C# y arquitectura limpia en .NET para las Web APIs consumidas por la aplicación móvil.

#### Nomenclatura
- **Clases y Métodos**: `PascalCase` (ej. `OrderService`, `GetOrderById`).
- **Variables**: `camelCase` (ej. `orderList`, `currentUserId`).
- **Interfaces**: Prefijo `I` (ej. `IOrderRepository`).

#### APIs RESTful para Móviles
- Respuestas en formato JSON ligero optimizadas para consumo móvil.
- Uso estándar de códigos de estado HTTP (`200 OK`, `201 Created`, `400 Bad Request`, `401 Unauthorized`, `404 Not Found`).

#### 5.1.4. Software Deployment Configuration

En esta sección se describe la configuración del despliegue y distribución de la solución móvil **FruitLogix**, detallando el proceso de compilación, empaquetado y entrega de los productos digitales a partir de sus repositorios de código fuente.

#### Despliegue y Distribución de la Aplicación Móvil (Android)

Para la distribución de la aplicación en entornos de prueba y entrega final, se establece el siguiente procedimiento:

1. **Compilación de Artefactos**:
   - Generación de archivos **APK** (Android Package) firmados para distribución interna de pruebas.
   - Generación del formato **AAB** (Android App Bundle) optimizado para publicación en tiendas.
2. **Firmado de Aplicación**:
   - Configuración del archivo `keystore` y claves de firmado mediante variables de entorno seguras en la fase de Build (`release` buildType).
3. **Distribución en Entorno de Pruebas**:
   - Publicación de releases ejecutable (APKs de prueba) mediante **GitHub Releases** o **Firebase App Distribution**, permitiendo a los *stakeholders* y al equipo QA instalar la app en dispositivos físicos.
4. **Publicación en Tienda (Producción / Internal Testing)**:
   - Configuración de la ficha de la app en **Google Play Console**.
   - Carga del paquete `.aab` en el canal de pruebas internas (Internal Testing Track) para validación de la solución en la Play Store.

#### Consideraciones Móviles
- El artefacto entregado debe ser compatible con versiones de Android 8.0 (API Level 26) o superior.
- Control de versiones mediante el archivo `build.gradle.kts` incrementando el `versionCode` (entero para la tienda) y actualizando el `versionName` (ej. `1.0.0`) en cada entrega relevante.
