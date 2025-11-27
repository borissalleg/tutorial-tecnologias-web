# 🐳 **Introducción a Docker** 

**Empaqueta tu código y olvídate de los "¡En mi máquina sí funciona!"**

> *Tutorial educativo para principiantes — sin conocimientos previos necesarios.*

---

## 🤔 **¿Qué es Docker?**

Imagina que estás desarrollando una aplicación: una página web, un bot de Telegram, un script de análisis de datos… Todo va bien *en tu computadora*. Pero cuando le pasas el código a un compañero, o intentas subirlo a un servidor… ¡falla! 😩  
¿Por qué? Porque tu computadora y la de los demás tienen distintas versiones de programas, librerías o configuraciones.

👉 **Docker resuelve este problema.**

Docker es una herramienta que te permite **empaquetar una aplicación junto con todo lo que necesita para ejecutarse**:  

        - Tu código  
        - El lenguaje de programación (por ejemplo, Python 3.11)  
        - Las librerías y dependencias  
        - Archivos de configuración  
        - Incluso partes del sistema operativo que necesita

Todo esto se guarda en algo llamado un **contenedor**, que es como una *caja sellada y portable* que funciona **exactamente igual** en cualquier lugar que tenga Docker instalado.

📦 Piensa en Docker como las **cajas de envío estandarizadas** que usan los barcos:  
No importa qué contengan (muebles, frutas, motores), todas tienen el mismo tamaño y se manejan igual.  
De la misma forma, un contenedor de Docker se puede mover entre tu laptop, la nube, un servidor… ¡y seguirá funcionando sin cambios!

---

## 🌟 **¿Por qué aprender Docker?**

        ✅ Evita el famoso: *"¡En mi máquina sí funciona!"*  
        ✅ Facilita el trabajo en equipo y la entrega de proyectos  
        ✅ Es usado en la industria por empresas como Netflix, Spotify, Google…  
        ✅ Te prepara para entornos modernos: desarrollo en la nube, microservicios, CI/CD

---

## 🚀 **Próximos pasos**

En los siguientes capítulos aprenderás:

1. Cómo **instalar Docker** (según tu sistema operativo)  
2. Los conceptos clave: *imágenes*, *contenedores*, *Dockerfile* y *Docker Hub*  
3. A crear tu primer contenedor con una app sencilla (¡Hola Mundo con Python o Node.js!)  
4. Consejos comunes y errores frecuentes (y cómo solucionarlos 😊)

📌 *Listo para empaquetar como un pro? ¡Sigamos!* 👇


???+ info "Introducción a Docker"
    === "Contenedores"

        **¿Qué es un contenedor? ¿Y en qué se diferencia de una Máquina Virtual?**

        🔹 **Contenedor**

            Es una unidad ligera y aislada de software que empaqueta una aplicación junto con todas sus dependencias (librerías, binarios, archivos de configuración) sobre el mismo kernel del sistema operativo host.
            
            Ejecuta procesos de forma aislada, pero comparte el kernel del sistema anfitrión.

           -  Características clave:

                ⚡ Ligero: Inicia en segundos.
                📦 Portátil: Funciona igual en desarrollo, pruebas y producción.
                🧱 Aislamiento de procesos y filesystem (mediante namespaces y cgroups en Linux).
                📉 Bajo overhead: Consume pocos recursos adicionales.
        
        💻 **Máquina Virtual (VM)**

            Una máquina virtual es un entorno completamente aislado que simula un hardware físico completo (CPU, memoria, disco, red), 
            
            y ejecuta un sistema operativo invitado completo sobre un hipervisor.

            ✅ Características clave:

            🛡️ Aislamiento fuerte (nivel de hardware).
            🖥️ Cada VM tiene su propio kernel y sistema operativo.
            ⏳ Arranque lento (decenas de segundos o minutos).
            📦 Alto consumo de CPU, RAM y almacenamiento.
        
        - Problemas de los silos entre desarrollo y operaciones.
            <iframe width="560" height="315" src="https://www.youtube.com/embed/tcTPRuUBQ4g?si=4OIyrE9Hpg-5qS7B" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
            ![Docker](https://www.youtube.com/watch?v=n32vN84KXJ8)
            https://www.youtube.com/watch?v=tcTPRuUBQ4g
    
    === "Imagenes"
        **Imágenes (Images)**
           
        Una imagen es una plantilla solo lectura que define cómo será un contenedor. Incluye:

            - Sistema de archivos mínimo (ej: alpine, ubuntu)
            - Código de la aplicación
            - Dependencias (librerías, binarios)
            - Metadatos (variables de entorno, comandos de inicio)

            🔍 Características
                ✅ Inmutables: una vez creada, no cambia.
                🧱 Compuesta por capas (cada instrucción en el Dockerfile crea una capa).
                🏷️ Identificada por un nombre y una etiqueta (ej: nginx:1.25-alpine).
        
        
        **Comandos Comunes**

        Listar imágenes locales
                
                docker images

        Descargar una imagen de Docker Hub

                docker pull redis:7-alpine

        Construir una imagen desde un Dockerfile
                
                docker build -t mi-app:1.0

        Eliminar una imagen
                
                docker rmi mi-app:1.0

    === "Contenedores1"
        🧊 Contenedores (Containers)
        Un contenedor es una instancia en ejecución de una imagen. Es un proceso aislado que:

        Tiene su propio filesystem (lectura-escritura sobre la imagen base),
        Su propia red, PID, usuario, etc. (gracias a namespaces),
        Y límites de recursos (CPU, RAM) definidos por cgroups.
        🔄 Ciclo de vida típico
        bash


        # Crear y ejecutar un contenedor en segundo plano (-d)
        docker run -d --name db -p 5432:5432 postgres:15

        # Listar contenedores en ejecución
        docker ps

        # Ver logs
        docker logs db

        # Detener y eliminar
        docker stop db && docker rm db
        💡 Un contenedor no persiste datos por defecto: al eliminarse, se pierde todo lo escrito en su filesystem (excepto si usas volúmenes).
        
    === "Volumenes"

        💾 Volúmenes (Volumes)

        Los volúmenes son la forma recomendada de persistir datos generados por contenedores (ej: bases de datos, archivos subidos).

            Tipos comunes:
            volume
            (gestionado por Docker)
            ✅ Producción (mejor rendimiento y portabilidad)
            bind mount
            (monta una carpeta del host)
            ✅ Desarrollo (ej: código en tiempo real)
            tmpfs
            (almacenamiento en RAM)
            Datos efímeros (seguridad, velocidad)

            Ejemplo: Persistir datos de PostgreSQL
            bash


            # Crear un volumen gestionado
            docker volume create pgdata

            # Iniciar PostgreSQL con el volumen
            docker run -d \
            --name postgres \
            -e POSTGRES_PASSWORD=secreto \
            -v pgdata:/var/lib/postgresql/data \
            postgres:15
            → Los datos sobreviven aunque el contenedor se elimine.

    === "Redes"
        🌐 Redes (Networks)
        Docker provee redes virtuales para que los contenedores se comuniquen entre sí y con el exterior.

        Tipos de redes:
        bridge
        (por defecto)
        Red privada para contenedores en el mismo host. Se usa
        -p
        para exponer puertos.
        host
        El contenedor comparte la red del host (sin aislamiento). Alto rendimiento, bajo aislamiento.
        none
        Sin red. Totalmente aislado.
        overlay
        Para contenedores en múltiples hosts (usado con Docker Swarm/Kubernetes).
        custom bridge
        ✅ Recomendado para apps multi-contenedor (resolución DNS automática por nombre).

        Ejemplo: Red personalizada
        bash



        # Crear red
        docker network create mi-red

        # Ejecutar dos servicios en la misma red
        docker run -d --name api --network mi-red node-app
        docker run -d --name db   --network mi-red postgres

        # Desde 'api', puedes acceder a 'db' usando el nombre: http://db:5432
        ✅ Ventaja: resolución DNS integrada — no necesitas IPs fijas.


## 🐳 ¿Qué es Docker?

**Docker** es una plataforma que te permite empaquetar tu aplicación con todo lo que necesita para funcionar (código, librerías, configuraciones) en una caja ligera llamada **contenedor**.

✅ Funciona igual en tu laptop, en la de tu compañero, en la nube…  
✅ Arranca en segundos  
✅ No afecta el resto de tu sistema  

> 📦 Piensa en Docker como un *"USB ejecutable"* de tu app.

---

### 🔹 Contenedor vs. Máquina Virtual (VM)

| Característica          | Contenedor                          | Máquina Virtual (VM)               |
|-------------------------|-------------------------------------|------------------------------------|
| **Nivel de aislamiento** | A nivel de proceso/filesystem       | A nivel de hardware                |
| **Kernel**              | Comparte el del host                | Tiene su propio kernel             |
| **Tamaño**              | MBs (ej: `nginx`: ~150 MB)          | GBs (ej: Ubuntu ISO: ~2–4 GB)      |
| **Arranque**            | Milisegundos a segundos             | Segundos a minutos                 |
| **Overhead**            | Muy bajo                            | Alto (CPU, RAM, disco)             |

> 💡 **Analogía**:  
> - Una **VM** es como alquilar un *departamento completo* (con cocina, baño, etc.).  
> - Un **contenedor** es como alquilar un *cuarto amueblado* en una casa compartida.

---

## 🏗️ Arquitectura y componentes de Docker

Docker funciona con una arquitectura **cliente-servidor**: