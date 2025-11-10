

## 🔹 **Unidad 1: Arquitecturas de Software y Fundamentos de DevOps**

### 🎯 **Objetivo específico**
Comprender los principales estilos arquitectónicos de software y establecer las bases culturales, organizacionales y técnicas del enfoque DevOps para entornos modernos de desarrollo.

### 📌 **Resultados de aprendizaje**
Al finalizar esta unidad, el estudiante será capaz de:

1. Comparar diferentes estilos arquitectónicos y seleccionar el adecuado según el contexto.
2. Explicar los principios y beneficios de la cultura DevOps frente a modelos tradicionales.
3. Identificar las plataformas y buenas prácticas para el despliegue de aplicaciones según su arquitectura.
4. Aplicar flujos de trabajo colaborativos con repositorios remotos.
   
### 📚 **Contenido temático**

???+ info "1.1 Estilos arquitectónicos de software"
    - **Arquitectura monolítica**
        - Ventajas y limitaciones.
    - **Arquitectura hexagonal (Puertos y Adaptadores)**
        - Separación entre lógica de negocio e interfaces.
    - **Cliente-Servidor**
        - Modelo clásico de solicitud-respuesta.
    - **Orientada a servicios (SOA)**
        - Servicios reutilizables y ESB.
    - **Serverless (FaaS)**
        - Ejecución sin gestión de servidores.
    - **Microservicios**
        - Principios: autonomía, escalabilidad, datos por servicio.
    -**Patrones: API Gateway, Circuit Breaker.**

???+ info "1.2 Introducción a DevOps"
    === "Origen del DevOps"
        - Problemas de los silos entre desarrollo y operaciones.
        - Influencia de Agile y Lean.
    === "Cultura DevOps"
        - Colaboración, responsabilidad compartida, mejora continua.
    === "Pilares CALMS"
        - Culture, Automation, Lean, Measurement, Sharing.
    === "Métricas clave"
        - MTTR, despliegues por día, Lead Time.

???+ info "1.3 Despliegue de Aplicaciones por Arquitectura"
    === "Tipo de arquitectura"
        - Aplicaciones monolíticas
        - Arquitecturas de microservicios
        - Aplicaciones serverless (FaaS)
    === "Plataformas de despliegue modernas"
        - Vercel: frontend y funciones serverless.
        - Railway: APIs y bases de datos rápidas.
        - AWS:
        - Elastic Beanstalk (monolitos)
        - S3 + CloudFront (sitios estáticos)
        - Lambda (serverless)
        - ECS / EKS (contenedores)
    === "Buenas prácticas"
        - Entornos: dev, staging, prod.
        - Gestión segura de secretos.
        - Dominios personalizados y HTTPS.
        - Automatización con CI/CD.
        - Monitoreo básico.

???+ info "1.4 Control de Versiones con Git"
    === "Conceptos básicos"
        - Repositorios locales y remotos.
        - Commits, ramas, merges, rebase.
        - Estado del repositorio.
    === "Flujos de trabajo"
        - GitFlow: main, develop, feature.
        - GitHub Flow: Trunk-Based Development.
    === "Buenas prácticas"
        - Mensajes claros, pull requests, .gitignore.
    === "Plataformas colaborativas"
        - GitHub, GitLab, Bitbucket.
        - Issues, code reviews, milestones.


---

## 🔹 **Unidad 2: Contenedores, Automatización y CI/CD**

### 🎯 **Objetivo específico**
Aplicar prácticas de contenerización, integración y entrega continua para automatizar el ciclo de vida del software, utilizando Docker y herramientas de CI/CD en entornos realistas.

### 📌 **Resultados de aprendizaje**
Al finalizar esta unidad, el estudiante será capaz de:
1. Contenerizar aplicaciones usando Docker y Dockerfile.
2. Orquestar servicios locales con Docker Compose.
3. Configurar pipelines de CI/CD en plataformas modernas.
4. Implementar estrategias de despliegue automatizado y seguro.

---

### 📚 **Contenido temático**

???+ info "2.1 Introducción a los Contenedores y Docker"
    === "Conceptos"
        - Virtualización vs contenedores.
        - Aislamiento: cgroups y namespaces.
        - Beneficios: portabilidad, eficiencia.
    === "Arquitectura de Docker"
        - Docker Engine, Cliente, Daemon, Host.
    === "Componentes clave"
        - Imágenes, contenedores, volúmenes, redes.
        - Registros: Docker Hub.
    === "Comandos esenciales"
        - `docker run`, `ps`, `build`, `push`, `exec`, `logs`.
    === "Dockerfile"
        - Instrucciones: `FROM`, `COPY`, `RUN`, `CMD`, `EXPOSE`.
        - Buenas prácticas: capas, tamaño, seguridad.
    === "Docker Compose"
        - Archivo `docker-compose.yml`.
        - Orquestación local de múltiples servicios.

???+ info "2.2 Integración y Entrega Continua (CI/CD)"
    === "Conceptos fundamentales"
        - CI: Integración Continua.
        - CD: Entrega/Despliegue Continuo.
    === "Beneficios del pipeline"
        - Rapidez, calidad, colaboración.
    === "Componentes del pipeline"
        - Build → Test → Deploy → Notify.
    === "Estrategias de despliegue"
        - Rolling, Blue/Green, Canary, Feature Flags.
    === "Herramientas"
        - GitHub Actions, GitLab CI, Jenkins.
    === "Configuración de pipelines"
        - Archivos YAML (ej: `.github/workflows/ci.yml`).
        - Jobs, steps, runners, secretos.
    === "Buenas prácticas"
        - Pruebas rápidas, inmutabilidad, DevSecOps.
    === "Integración con contenedores"
        - CI/CD para aplicaciones containerizadas.
        - Pipelines para microservicios.



## 📝 **Propuesta Evaluativa**

A continuación, se presentan tres actividades evaluativas que permiten medir el logro de los resultados de aprendizaje de manera progresiva, integradora y práctica.

La realización en grupo no es opcional, esta resulta ser obligatoria debido a las competencias de trabajo colaborativo que se deben desarrollar y fortalecer, el docente explicará como conformar los grupos y entregar la actividad.

---

### ✅ Actividad 1: Análisis Comparativo de Arquitecturas y Plan de Despliegue

**Tipo:** Actividad en Grupo (minimo 3 maximo 5 integrantes)

**Ponderación:** 35%

**Unidades asociadas:** Unidad 1

#### 🎯 Objetivo
Evaluar la capacidad del estudiante para comparar arquitecturas de software y proponer estrategias de despliegue acordes al contexto tecnológico.

#### 📌 Descripción
El estudiante deberá:

1. Seleccionar una aplicación existente (ej: tienda online, sistema de gestión académica).

2. Proponer dos opciones arquitectónicas (monolítica vs microservicios o serverless).

3. Comparar ambas opciones en términos de escalabilidad, mantenimiento, costo y operación.

4. Elegir una plataforma de despliegue (Vercel, Railway o AWS) según la arquitectura seleccionada.

5. Redactar un informe técnico (máx. 3 páginas) con:
   - Diagrama de arquitectura propuesto.
   - Justificación de la elección.
   - Plan de despliegue con buenas prácticas (entornos, secretos, dominios).

6. Sustentacion del Informe tecnico mediante video de 5 minutos donde participen todos los integrantes del grupo



#### 📊 Rúbrica de Evaluación – Actividad 1: Análisis Comparativo de Arquitecturas y Plan de Despliegue

| Criterios | 40 pts (Excelente) | 20 pts (Parcial) | 0 pts (No cumple) |
|---------|--------------------|------------------|-------------------|
| **Claridad y profundidad del análisis** | El informe presenta una comparación clara, profunda y bien fundamentada entre arquitecturas. Justifica con detalle el modelo de solución propuesto y explica coherentemente el uso y la elección de tecnologías web. | La comparación es básica o incompleta. Se mencionan tecnologías, pero sin profundizar en su aplicación o justificación. | Aunque se presenta un informe, este no cuenta con los componentes explicativos necesarios para indicar cómo se adoptan y usan las tecnologías web para el modelo de solución. |
| **Coherencia entre arquitectura y plataforma de despliegue** | La elección de la plataforma de despliegue (Vercel, Railway, AWS, etc.) está completamente alineada con la arquitectura seleccionada. Se justifica con argumentos técnicos sólidos. | Existe cierta relación entre arquitectura y plataforma, pero con justificación débil o errores de adecuación. | No hay coherencia entre la arquitectura propuesta y la plataforma de despliegue; la elección es inapropiada o no justificada. |
| **Aplicación de buenas prácticas** | Se aplican exhaustivamente buenas prácticas: gestión de entornos (dev/staging/prod), uso seguro de secretos, HTTPS, dominios personalizados y automatización CI/CD. | Se mencionan algunas buenas prácticas, pero no todas están implementadas o justificadas. | No se aplican ni se mencionan buenas prácticas de despliegue ni seguridad. |
| **Calidad del informe y diagramas** | El informe es claro, profesional y bien estructurado. Incluye diagramas legibles (arquitectura, flujos) que refuerzan la comprensión del modelo. | El informe tiene fallas de redacción o estructura. Los diagramas son poco claros o están ausentes. | El informe carece de organización, claridad o diagramas útiles para entender la solución. |
| **Calidad de Sustentación en grupo** | La presentación oral es clara, coordinada y demuestra dominio del tema. Todos los miembros participan y responden preguntas con precisión técnica. | La sustentación es aceptable, pero con falencias en coordinación, dominio técnico o participación desigual. | La sustentación carece de claridad, no responde preguntas clave o no hay participación equitativa del grupo. |

---

### ✅ Actividad 2: Contenerización de una Aplicación Web

**Tipo:** Actividad en Grupo (minimo 3 maximo 5 integrantes)
**Ponderación:** 35%  
**Duración:** 10 días  
**Unidades asociadas:** Unidad 2

#### 🎯 Objetivo
Evaluar la habilidad para contenerizar aplicaciones usando Docker y Docker Compose, garantizando entornos consistentes y reproducibles.

#### 📌 Descripción
El equipo deberá:

1. Tomar una aplicación full-stack simple (frontend + backend + base de datos).

2. Crear `Dockerfile` para cada componente.

3. Definir un archivo `docker-compose.yml` para orquestar los servicios.

4. Documentar los pasos para construir y levantar el sistema.

5. Subir el código a un repositorio público (GitHub/GitLab) con README detallado.

> 💡 Puede usarse una app de ejemplo como un blog con React + Node.js + MongoDB. o una Aplicación desarrollada con anterioridad con cualquier lenguaje o tecnologia.

#### 🔧 Entregables
- Repositorio con código, Dockerfiles y docker-compose.yml.
- Video corto (3-5 min) mostrando el despliegue local.
- Informe breve de configuración y pruebas.
- Sustentacion del Informe tecnico mediante video de 5 minutos donde participen todos los integrantes del grupo

### 📊 *Rúbrica de Evaluación – Actividad 2: Contenerización de una Aplicación Web*

| Criterios | 40 pts (Excelente) | 20 pts (Parcial) | 0 pts (No cumple) |
|---------|--------------------|------------------|-------------------|
| **Funcionalidad completa de la app contenerizada** | La aplicación se construye y ejecuta sin errores. Todos los servicios (frontend, backend, base de datos) están activos y comunicándose correctamente. Acceso completo a través del navegador. | Algunos servicios funcionan, pero hay problemas de conexión o configuración que requieren ajustes manuales para su funcionamiento. | La aplicación no se inicia o presenta fallos críticos que impiden su uso. No hay evidencia funcional. |
| **Calidad y buenas prácticas en Dockerfiles** | Los `Dockerfile` siguen buenas prácticas: imágenes base específicas (no `latest`), capas optimizadas, uso de `.dockerignore`, multi-stage build si aplica, y exposición correcta de puertos. | Los `Dockerfile` permiten construir las imágenes, pero carecen de optimización o seguridad (ej: credenciales expuestas, imágenes pesadas). | No se usan `Dockerfile` o están mal estructurados, generando errores o vulnerabilidades. |
| **Correcta orquestación con Docker Compose** | El archivo `docker-compose.yml` define claramente servicios, redes, volúmenes y dependencias. Permite levantar toda la aplicación con un solo comando y reinicios automáticos. | El archivo tiene errores menores (redes mal definidas, volúmenes no persistentes) que afectan parcialmente el despliegue. | No existe `docker-compose.yml` o este no funciona; los servicios no pueden orquestarse juntos. |
| **Documentación y claridad del proceso** | El repositorio incluye un `README.md` completo: instrucciones claras, capturas, diagramas y explicaciones técnicas. El código está organizado y bien comentado. | La documentación es básica o poco clara. Falta información necesaria para replicar el entorno sin ayuda externa. | No hay documentación o es mínima. No se puede entender cómo ejecutar el proyecto. |
| **Colaboración en equipo y gestión del repositorio** | Historial de Git muestra commits colaborativos, ramas, pull requests y revisiones de código. Uso adecuado de flujos de trabajo (GitHub Flow). | Participación desigual o pocos commits por miembro. Falta seguimiento de buenas prácticas de Git. | Un solo estudiante realizó todo el trabajo. No hay evidencia de trabajo conjunto ni uso colaborativo de Git. |

---

#### ✅ Actividad 3: Pipeline CI/CD Automatizado

**Tipo:** Actividad en Grupo (minimo 3 maximo 5 integrantes)  

**Ponderación:** 30%  
  
**Unidades asociadas:** Unidad 2

#### 🎯 Objetivo
Evaluar la capacidad para implementar un pipeline de CI/CD que automatice pruebas, construcción y despliegue.

#### 📌 Descripción
El equipo deberá:

1. Configurar un pipeline CI/CD usando GitHub Actions o GitLab CI.
2. El pipeline debe:
      - Ejecutar pruebas automáticas al hacer push.
      - Construir imágenes de Docker.
      - Desplegar el frontend en Vercel o el backend en Railway/AWS.
3. Usar variables de entorno y secretos de forma segura.
4. Implementar una estrategia de despliegue (blue/green o canary – simulada o parcial).

#### 🚀 Entregables
- Enlace al repositorio con el pipeline configurado.
- Capturas de ejecución del pipeline.
- Informe técnico que explique:
    - Flujo del pipeline.
    - Herramientas usadas.
    - Estrategia de despliegue aplicada.
- Sustentacion del Informe tecnico mediante video de 5 minutos donde participen todos los integrantes del grupo


## 📊 Rúbrica de Evaluación – Actividad 3: Pipeline CI/CD Automatizado

| Criterios | 40 pts (Excelente) | 20 pts (Parcial) | 0 pts (No cumple) |
|---------|--------------------|------------------|-------------------|
| **Automatización efectiva del pipeline** | El pipeline se ejecuta automáticamente al hacer `push` o `pull request`. Incluye etapas completas: build, test, deploy. Notificaciones funcionales (email, Slack, etc.). | El pipeline se ejecuta pero con errores o faltan etapas clave (ej: no realiza pruebas o no notifica). | No hay pipeline configurado o este no se activa automáticamente. |
| **Integración correcta con contenedores** | El pipeline construye imágenes de Docker correctamente, las etiqueta con versiones y las sube a un registro (Docker Hub o similar). | Se usan contenedores, pero con errores (imágenes no versionadas, sin push al registro). | No hay integración con Docker ni empaquetado del entorno. |
| **Aplicación de buenas prácticas de seguridad** | Uso seguro de variables de entorno y secretos (no expuestos en código). Acceso restringido al pipeline. Validación de dependencias (SCA/SAST si aplica). | Se usan secretos, pero con riesgos (ej: mal configurados, comentarios revelan datos). | Credenciales o claves están expuestas en el código o archivos de configuración. |
| **Elección y explicación de la estrategia de despliegue** | Se implementa o simula una estrategia avanzada (blue/green, canary) con documentación clara sobre su funcionamiento y beneficios. | La estrategia está mencionada pero no implementada completamente o sin justificación técnica. | No se aplica ni se explica ninguna estrategia de despliegue más allá del deploy directo. |
| **Claridad del informe y evidencias** | El informe técnico es claro, completo y bien estructurado. Incluye capturas del pipeline, diagramas y enlaces funcionales. Explica cada paso del flujo. | El informe tiene fallas de redacción o falta evidencia visual (capturas, enlaces). | No hay informe o es incompleto, sin evidencias que respalden el trabajo realizado. |

