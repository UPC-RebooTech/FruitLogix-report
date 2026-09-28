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

