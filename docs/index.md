# Manual: Tecnologías y Prácticas DevOps  


## Introducción al Curso: Tecnologías y Prácticas DevOps

Las aplicaciones modernas ya no se construyen como sistemas aislados o monolíticos. Hoy, el software se desarrolla en entornos dinámicos, distribuidos y altamente escalables, donde la arquitectura elegida —como los microservicios o el modelo serverless— impacta directamente en cómo se desarrolla, prueba, despliega y opera. En este escenario, las prácticas tradicionales de desarrollo y operaciones han quedado obsoletas, dando paso a un nuevo paradigma: DevOps.

Este curso tiene como propósito formar ingenieros de sistemas capaces de comprender y aplicar las tecnologías y metodologías clave del desarrollo moderno de software. Comenzamos explorando los principales estilos arquitectónicos, con especial énfasis en los microservicios, para entender por qué la colaboración entre equipos de desarrollo y operaciones es más necesaria que nunca. A partir de esta base conceptual, avanzamos hacia las herramientas y prácticas que permiten entregar software de forma rápida, segura y confiable.

A lo largo del curso, los estudiantes dominarán el control de versiones con Git, implementarán pipelines de integración y entrega continua (CI/CD) utilizando plataformas como GitHub Actions o GitLab CI, y aprenderán a empaquetar y desplegar aplicaciones mediante contenedores con Docker y orquestación básica con Kubernetes. Todo ello en un marco de trabajo colaborativo, ágil y orientado a la automatización.

El enfoque es profundamente práctico, con laboratorios, proyectos reales y casos de estudio inspirados en el ecosistema tecnológico colombiano. El objetivo no es solo enseñar herramientas, sino formar profesionales con una mentalidad DevOps: proactivos, colaboradores y preparados para enfrentar los desafíos de la transformación digital en empresas, startups y el sector público.

Bienvenidos a un curso donde la arquitectura, la cultura y la tecnología se unen para construir el futuro del software.

### 🧩 Habilidades desarrolladas

- Gestionar eficazmente el código fuente en entornos colaborativos.
- Automatizar la construcción, prueba y despliegue de software.
- Empaquetar aplicaciones en contenedores para garantizar consistencia entre entornos.
- Comprender los fundamentos de la orquestación moderna con Kubernetes.


## 🔹 Unidad 1: Arquitecturas de Software y Fundamentos de DevOps

### 🎯 Objetivo específico
Comprender los principales estilos arquitectónicos de software, con énfasis en microservicios, y establecer las bases culturales y organizacionales del enfoque DevOps para entornos modernos de desarrollo.

---

### 📚 Contenido temático

???+ info #### "1.1 Estilos arquitectónicos de software"

  - **Arquitectura monolítica**
    - Estructura única y acoplada.
    - Ventajas: simplicidad, despliegue unitario.
    - Limitaciones: escalabilidad limitada, mantenimiento complejo.
    - Casos de uso: aplicaciones pequeñas o internas.

  - **Cliente-Servidor**
    - Separación clara entre interfaz (cliente) y lógica (servidor).
    - Comunicación mediante solicitudes HTTP/HTTPS.
    - Aplicaciones web tradicionales y móviles.

  - **Orientada a servicios (SOA)**
    - Servicios reutilizables comunicados vía ESB (Enterprise Service Bus).
    - Granularidad gruesa.
    - Usada en entornos empresariales legacy.

  - **Serverless (FaaS)**
    - Ejecución sin gestión de servidores.
    - Pago por uso (ej: AWS Lambda, Azure Functions).
    - Ideal para tareas event-driven o de corta duración.

  - **Microservicios**
    - Arquitectura basada en servicios pequeños, independientes y especializados.
    - **Principios clave**:
      - Desacoplamiento
      - Autonomía técnica y organizacional
      - Escalabilidad por servicio
      - Datos gestionados por cada servicio
    - **Comunicación**:
      - Síncrona: REST, gRPC
      - Asíncrona: mensajería (Kafka, RabbitMQ)
    - **Patrones comunes**:
      - API Gateway
      - Service Discovery
      - Circuit Breaker
      - Config Server
    - **Desafíos**:
      - Complejidad operacional
      - Consistencia eventual
      - Monitoreo distribuido
      - Trazabilidad de peticiones

???+ info "#### 1.2 Introducción al DevOps"
  - **Origen del DevOps**
  - Surgimiento ante la ineficiencia de silos entre desarrollo y operaciones.
  - Influencia de metodologías ágiles y Lean.

- **Cultura DevOps**
  - Colaboración interdisciplinaria.
  - Responsabilidad compartida por el software en producción.
  - Mentalidad de mejora continua.

- **Pilares CALMS**
  - **C**ulture: trabajo en equipo, confianza.
  - **A**utomation: automatizar todo lo repetible.
  - **L**ean: eliminar desperdicios, optimizar flujos.
  - **M**easurement: métricas para tomar decisiones.
  - **S**haring: conocimiento abierto y retroalimentación constante.

- **Métricas clave**
  - **MTTR (Mean Time to Recovery)**: tiempo promedio para recuperarse de una falla.
  - **Despliegues por día**: frecuencia de entrega.
  - **Lead Time for Changes**: tiempo desde el commit hasta producción.
  - **Change Failure Rate**: porcentaje de despliegues que generan fallos.

- **Adopción de DevOps en Colombia**
  - Empresas líderes: Bancolombia, Rappi, Éxito Digital.
  - Centros de innovación: Ruta N (Medellín), Apps.co.
  - Retos: falta de cultura DevOps en PYMES, brecha de habilidades técnicas.
  - Oportunidades: crecimiento del sector fintech, gobierno digital y startups.

g
### 💡 Actividades sugeridas

- **Taller práctico**: Comparar una aplicación monolítica vs microservicios mediante diagramas de arquitectura y .
- **Análisis de caso**: "La migración a microservicios en Rappi Colombia".
- **Debate grupal**: ¿Cuándo conviene adoptar microservicios? ¿Y cuándo no?

---

### 🧩 Habilidades desarrolladas

- Identificar el estilo arquitectónico más adecuado según el contexto del proyecto.
- Reconocer cómo la arquitectura impacta en la operación, mantenimiento y escalabilidad del software.
- Comprender la filosofía DevOps como una evolución cultural y técnica del desarrollo de software.

---

## 🔹 Unidad 2: Control de Versiones y CI/CD con Contenedores

### 🎯 Objetivo específico
Aplicar prácticas de control de versiones y automatización mediante pipelines de integración y entrega continua, utilizando contenedores para garantizar entornos consistentes y reproducibles.

---

### 📚 Contenido temático

#### 2.1 Control de versiones con Git

- **Conceptos básicos**
  - Repositorios locales y remotos.
  - Commits, ramas, merges, rebase.
  - Estado del repositorio: working directory, staging area, HEAD.

- **Flujos de trabajo**
  - **GitFlow**:
    - Ramas: `main`, `develop`, `feature`, `release`, `hotfix`.
    - Ideal para proyectos con ciclos de lanzamiento definidos.
  - **GitHub Flow / Trunk-Based Development**:
    - Rama principal (`main`) siempre desplegable.
    - Pull requests para revisión de código.
    - Más ágil, ideal para CI/CD continuo.

- **Buenas prácticas**
  - Mensajes de commit claros y descriptivos.
  - Pull requests con revisiones de pares.
  - Protección de ramas críticas.
  - Uso de `.gitignore` y convenciones de escritura (Conventional Commits).

- **Plataformas colaborativas**
  - GitHub, GitLab, Bitbucket.
  - Gestión de equipos, issues, milestones y code reviews.

#### 2.2 Integración y Entrega Continua (CI/CD)

- **Conceptos clave**
  - **Integración Continua (CI)**: integrar cambios frecuentemente con pruebas automáticas.
  - **Entrega Continua (CD)**: tener el software siempre listo para producción.
  - **Despliegue Continuo**: despliegue automático a producción tras pasar pruebas.

- **Estructura de un pipeline CI/CD**