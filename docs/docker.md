# 🐳 **Introducción a Docker** 

**Empaqueta tu código y olvídate de los "¡En mi máquina sí funciona!"**

> *Tutorial educativo para principiantes — sin conocimientos previos necesarios.*

---

## 🤔 **¿Qué es Docker?**

Imagina que estás desarrollando una aplicación: una página web, un bot de Telegram, un script de análisis de datos… Todo va bien *en tu computadora*. Pero cuando le pasas el código a un compañero, o intentas subirlo a un servidor… ¡falla! 😩  
¿Por qué? Porque tu computadora y la de los demás tienen distintas versiones de programas, librerías o configuraciones.


## 📦 Imágenes, contenedores, volúmenes y redes

| Concepto | ¿Qué es? | Analogía 🍕 |
|---------|----------|-------------|
| **Imagen** | Plantilla *solo lectura* (como una receta de pizza) | 📜 *"Masa + salsa + queso + pepperoni"* |
| **Contenedor** | Instancia *en ejecución* de una imagen (la pizza horneada y lista para comer) | 🍕 *"Tu pizza personal, recién salida del horno"* |
| **Volumen** | Carpeta *persistente* para guardar datos (ej: base de datos) | 🥡 *"Caja para llevar: los datos sobreviven aunque apagues el horno"* |
| **Red** | Permite que contenedores se hablen entre sí (o con el exterior) | 📡 *"WiFi del restaurante: tu pizza (contenedor) puede pedir más queso a la cocina (base de datos)"* |

---

???+ info "Introducción a Docker"
    === "Conceptos"

        🐳 ¿Qué es Docker?"

        **Docker** es una plataforma que te permite empaquetar tu aplicación con todo lo que necesita para funcionar (código, librerías, configuraciones) en una caja ligera llamada **contenedor**.

        ✅ Funciona igual en tu laptop, en la de tu compañero, en la nube…  
        ✅ Arranca en segundos  
        ✅ No afecta el resto de tu sistema  

        > 📦 Piensa en Docker como un *"USB ejecutable"* de tu app.

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

        Aprender Docker bien no se trata de memorizar comandos, sino de entender una mentalidad: aislar, reproducir y escalar aplicaciones de forma predecible.

        Y tú, con tu perfil (académico, trabajando en grupo, con interés práctico y experiencia previa en limitaciones técnicas), tienes el contexto perfecto para sacarle máximo provecho.

        ## 🚀 **Próximos pasos**

        En los siguientes capítulos aprenderás:

        1. Cómo **instalar Docker** (según tu sistema operativo)  
        2. Los conceptos clave: *imágenes*, *contenedores*, *Dockerfile* y *Docker Hub*  
        3. A crear tu primer contenedor con una app sencilla (¡Hola Mundo con Python o Node.js!)  
        4. Consejos comunes y errores frecuentes (y cómo solucionarlos 😊)

        📌 *Listo para empaquetar como un pro? ¡Sigamos!* 👇
        ---

        === "**Contenedor**"
         
            Es una unidad ligera y aislada de software que empaqueta una aplicación junto con todas sus dependencias (librerías, binarios, archivos de configuración) sobre el mismo kernel del sistema operativo host.

            ![contenedor](https://www.prored.es/wp-content/uploads/2019/01/prored-esquema-arquitectura-contenedor-software.png)
                
                        
            Ejecuta procesos de forma aislada, pero comparte el kernel del sistema anfitrión.

            🔹 **Características clave:**
                        
             - ⚡**Ligero:** Inicia en segundos.

             - 📦 **Portátil:** Funciona igual en desarrollo, pruebas y producción.

             - 🧱 **Aislamiento**  de procesos y filesystem (mediante namespaces y cgroups en Linux).
                
             - 📉 **Bajo overhead:** Consume pocos recursos adicionales.

        
        === "💻**Máquina Virtual (VM)**"

            Una máquina virtual es un entorno completamente aislado que simula un hardware físico completo (CPU, memoria, disco, red), y ejecuta un sistema operativo invitado completo sobre un hipervisor.

            ![Maquina Virtual](https://www.ufsexplorer.com/es/img/articles/vmdo/virtual-machine-basics.jpg)

        
            🔹 ✅ Características clave:

            🛡️ Aislamiento fuerte (nivel de hardware).
            🖥️ Cada VM tiene su propio kernel y sistema operativo.
            ⏳ Arranque lento (decenas de segundos o minutos).
            📦 Alto consumo de CPU, RAM y almacenamiento.
                

        === "Contenedor Vs Maquina Virtual"
           
            ### 🔹 Contenedor vs. Máquina Virtual (VM)

            # 🐳 ¿Contenedor o Máquina Virtual?  
            ## La diferencia que salva tus noches antes de la entrega

            Imagina esto:
            > Estás trabajando en un proyecto grupal.  
            > Tu código funciona **perfecto** en tu laptop.  
            > Lo pasas a tu compañero… y dice:  
            > ❌ *“No me corre.”*  
            > ❌ *“Me falta una librería.”*  
            > ❌ *“¿Tú usas Windows? Yo, Linux… ah, sí, por eso.”*  

            **contenedores** y **máquinas virtuales (VMs)** son dos formas de resolver *exactamente ese problema*.  
            Pero lo hacen de maneras muy distintas… y una es mucho más ligera, rápida y amigable para estudiantes 🎓.

            Vamos a compararlas como si fueran *alojamientos* —porque al final, ambas “alojan” tu aplicación.
            ---
            ## 🏠 Analogía: ¿Departamento completo o cuarto en una casa compartida?

            | | **Máquina Virtual (VM)** | **Contenedor (ej: Docker)** |
            |---|--------------------------|-----------------------------|
            | 🏢 **Qué es** | Como alquilar un **departamento completo**: trae cocina, baño, calefacción, electricidad… ¡todo incluido! | Como alquilar un **cuarto amueblado** en una casa compartida: tienes tu espacio privado, pero compartes la cocina, el agua y la electricidad con los demás. |
            | 💻 **Qué incluye** | Un **sistema operativo completo** (Windows, Linux, etc.) + tu app + sus dependencias. | Solo tu **app y sus dependencias**… y usa el sistema operativo de la computadora *anfitriona*. |
            | ⏱️ **Velocidad** | Arranca en **segundos… o minutos** (como encender una laptop desde cero). | Arranca en **milisegundos** (como abrir una app en tu teléfono). |
            | 📦 **Tamaño** | Gigas (GB). Ej: una VM de Ubuntu pesa ~2–5 GB. | Megabytes (MB). Ej: una app web con Nginx: ~150 MB. |
            | 🔌 **Recursos** | Usa mucha RAM y CPU… aunque esté "en reposo". | Usa solo lo que necesita *en ese momento*. |
            | 🧪 **Ideal para…** | - Probar otro sistema operativo (ej: Windows en Mac)<br>- Aplicaciones legacy que necesitan un SO específico | - Desarrollo web/APIs<br>- Proyectos grupales<br>- Cualquier app moderna que quieras que *funcione igual en todas partes* |

            ---

            <iframe width="560" height="315" src="https://www.youtube.com/embed/tcTPRuUBQ4g?si=4OIyrE9Hpg-5qS7B" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
           

            ## 💡 En una frase (para tu cuaderno mental):

            > 🔹 **VM = Simular una computadora entera.**  
            > 🔹 **Contenedor = Empaquetar tu app como un “USB ejecutable” que corre en cualquier lugar.**

            ---

            ## 🎯 ¿Por qué esto importa para ti como estudiante?

            - ✅ Con **contenedores**, evitas la excusa de *“funciona en mi máquina”*.  
            - ✅ Tu grupo puede empezar en minutos: `git clone` + `docker-compose up` → ¡listo!  
            - ✅ No necesitas una laptop potente: Docker corre incluso en una Raspberry Pi.  
            - ✅ Es lo que usan empresas como Netflix, Spotify y Mercado Libre… así que **aprenderlo te da ventaja** en pasantías y trabajos.

        
            
    === "Imagenes"
        === "Imágenes (Images)"
           
            Una imagen es una plantilla solo lectura que define cómo será un contenedor. Incluye:

                ✅ Sistema de archivos mínimo (ej: alpine, ubuntu)

                ✅ Código de la aplicación

                ✅ Dependencias (librerías, binarios)

                ✅ Metadatos (variables de entorno, comandos de inicio)

            🔍 Características

                ✅ Inmutables: una vez creada, no cambia.

                🧱 Compuesta por capas (cada instrucción en el Dockerfile crea una capa).

                🏷️ Identificada por un nombre y una etiqueta (ej: nginx:1.25-alpine).

            === "Tipos de imágenes"

                | Tipo | Ejemplo | Pros | Contras | Recomendado para |
                |------|---------|------|---------|------------------|
                | **Oficial** | `nginx`, `redis`, `postgres` | ✅ Seguras, bien mantenidas, documentadas | ⚠️ Pueden ser grandes | Producción, aprendizaje |
                | **Slim / Alpine** | `python:3.11-slim`, `node:18-alpine` | ✅ Más pequeñas, menos vulnerabilidades | ⚠️ Alpine usa `musl` (no `glibc`) → puede romper algunas apps | Producción, CI/CD |
                | **Distroless** | `gcr.io/distroless/python3` | ✅ Mínimas (solo runtime + app), muy seguras | ❌ Sin shell → difícil debuggear | Alta seguridad (ej: bancos) |
                | **Multi-arquitectura** | `--platform linux/arm64` | ✅ Funcionan en Mac M1/M2, Raspberry Pi | — | Desarrollo en equipos con hardware mixto |

                > 💡 **Regla práctica para estudiantes**:  
                > Usa `alpine` o `slim` siempre que puedas.  
                > Ej: `python:3.11-slim`, no `python:3.11`.

                ---
        
            === "¿Cómo están construidas?"

                Las imágenes se arman como una **torta de capas** 🎂:

                    [ Capa 5: CMD ["node", "app.js"] ] ← Solo lectura (metadatos)

                    [ Capa 4: COPY . /app ]

                    [ Capa 3: RUN npm install ]

                    [ Capa 2: RUN apt-get install -y nodejs ]
                    
                    [ Capa 1: FROM node:18-slim ] ← Capa base (SO mínimo)

                ### ✅ Ventajas de las capas:
                - **Reutilización**: si `node:18-slim` ya está descargada, no se vuelve a bajar.  
                - **Caché inteligente**: si solo cambias tu código (capa 4), Docker reusa las capas 1–3 → ¡construcción más rápida!  
                - **Eficiencia en espacio**: 10 imágenes basadas en `alpine` comparten la misma capa base.

                > 🛠️ Ver capas de una imagen:  
                > ```bash
                > docker history nginx:alpine
                > ```
                ---

                > 🛠️ Construir  una imagen:

                > ```bash
                
                > docker build -t mi-app:1.0 .
                > # El `.` significa: "usa el Dockerfile en este directorio"
                >```
                ---

            === "¿Donde conseguirlas?"

                | Fuente | Cómo acceder | Ejemplo |
                |--------|--------------|---------|
                | **Docker Hub** (registro público) | `docker pull NOMBRE` | `docker pull redis:7-alpine` |
                | **Tu propio registro** (privado) | `docker pull mi-registro/imagen:tag` | `docker pull registry.gitlab.com/mi-proyecto/backend:latest` |
                | **Construidas localmente** | `docker build -t nombre .` | `docker build -t mi-app:dev .` |

                > 📌 Por defecto, `docker run nginx` hace:  
                > 1. Busca `nginx` localmente  
                > 2. Si no está → `docker pull nginx` implícito  
                > 3. Luego `docker run` con esa imagen

            
        === "Comandos Comunes"


            === "Comandos esenciales para imágenes"

                | Comando | Descripción | Ejemplo |
                |--------|-------------|---------|
                | `docker images` | Lista imágenes locales | `docker images` |
                | `docker pull IMAGEN[:TAG]` | Descarga una imagen | `docker pull postgres:15` |
                | `docker build -t NOMBRE .` | Construye una imagen desde `Dockerfile` | `docker build -t api-users .` |
                | `docker tag IMAGEN NUEVO_NOMBRE` | Renombra/etiqueta una imagen | `docker tag api-users mi-registro/api:1.0` |
                | `docker rmi IMAGEN` | Elimina una imagen | `docker rmi api-users` |
                | `docker save -o archivo.tar IMAGEN` | Exporta imagen a archivo | `docker save -o mi-app.tar mi-app:1.0` |
                | `docker load -i archivo.tar` | Importa imagen desde archivo | `docker load -i mi-app.tar` |

                > 🔍 Busca imágenes en Docker Hub: [https://hub.docker.com](https://hub.docker.com)

                ---
                Listar imágenes locales
                        
                        docker images

                Descargar una imagen de Docker Hub

                        docker pull redis:7-alpine

                Construir una imagen desde un Dockerfile
                        
                        docker build -t mi-app:1.0

                Eliminar una imagen
                        
                        docker rmi mi-app:1.0

       

        === "Cómo se construye una imagen"

            Un `Dockerfile` es un **script de texto plano** que define cómo construir una imagen.

            ### Ejemplo mínimo (app Python):
            ```dockerfile
                # Capa 1: Imagen base
                FROM python:3.11-slim

                # Capa 2: Establecer directorio de trabajo
                WORKDIR /app

                # Capa 3: Copiar dependencias (solo requirements.txt)
                COPY requirements.txt .

                # Capa 4: Instalar dependencias
                RUN pip install --no-cache-dir -r requirements.txt

                # Capa 5: Copiar código
                COPY . .

                # Capa 6: Exponer puerto (documentación)
                EXPOSE 5000

                # Capa 7: Comando por defecto
                CMD ["python", "app.py"]


            ```
        
        === "Como subir imagen a DockerHUB"
                    
            ✅ 1. Crear una cuenta en Docker Hub

            Si aún no la tienes:
            
            🔗 https://hub.docker.com/

            > Recuerda tu nombre de usuario (por ejemplo: ronaldlopez), pues lo necesitarás para nombrar la imagen.

            ✅ 2. Construir tu imagen localmente

            Supongamos que tienes un Dockerfile en tu directorio actual:

            ```bash
            docker build -t nombre-imagen:etiqueta .
            ```
            > ⚠️ Asegúrate de que el proceso termina sin errores (Successfully built ...).

            ✅ 3. Etiquetar la imagen con tu nombre de usuario de Docker Hub
            
            El formato debe ser:
            
                <usuario-dockerhub>/<nombre-repositorio>:<etiqueta>

            > Esto no crea una copia; solo agrega un alias al mismo ID de imagen.

            ✅ 4. Iniciar sesión en Docker Hub desde la terminal
            ```bash
            docker login
            ```
            Ingresa tu usuario y contraseña cuando se te pida.

            >💡 Si usas autenticación de 2 factores, deberás generar un Personal Access Token en Docker Hub y usarlo como contraseña.

            ✅ 5. Subir (push) la imagen
            ```bash
            docker push nombre_usuario/nombre-imagen:etiqueta .
            ```
            ✅ Listo. La imagen estará visible en:
                🔗 https://hub.docker.com/r/ronaldlopez/myapp

            ℹ️ Extra: Buenas prácticas

            > **Usa** etiquetas descriptivas (ej. v1.0, latest, 2026-01-02).

            > **Evita :** latest en entornos de producción; es mejor usar versiones específicas.

            > Si es una **imagen pública**, cualquiera podrá descargarla con docker pull ronaldlopez/myapp:v1.


    === "Contenedores1"
        === " Conceptos"
            # 🧊 ¿Qué es un contenedor?

            Un **contenedor** es un **entorno de ejecución ligero, aislado y portable** que empaqueta una aplicación junto con todas sus dependencias: código, bibliotecas, configuraciones y herramientas necesarias para ejecutarse.

            > 🔍 **Definición técnica**:  
            > Es una instancia en ejecución de una *imagen Docker*, construida sobre tecnologías de aislamiento del kernel de Linux (`namespaces`, `cgroups`, `UnionFS`), que permite ejecutar procesos de forma segura y reproducible, sin interferir con el sistema anfitrión ni con otros contenedores.

            ---

            ## 🤔 ¿Por qué son útiles los contenedores?

            Imagina esta situación común en desarrollo:

            > _“¡Pero en mi máquina sí funciona!”_  
            > — Frase célebre cuando una aplicación falla al pasar de desarrollo a pruebas, o de pruebas a producción.

            Este problema —conocido como **“works on my machine”**— ocurre porque los entornos difieren: versiones de SO, librerías, variables de entorno, permisos, etc.

            ### ✅ Los contenedores resuelven esto mediante:

            | Beneficio | Explicación |
            |----------|-------------|
            | **Reproducibilidad** | La misma imagen produce el mismo comportamiento en cualquier máquina con Docker (desarrollo, CI, producción). |
            | **Aislamiento** | Cada contenedor tiene su propio filesystem, red, procesos y usuarios. Un fallo o conflicto en uno no afecta a los demás. |
            | **Portabilidad** | Una imagen se construye una vez y se ejecuta en cualquier lugar: laptop, servidor físico, nube (AWS, Render, etc.). |
            | **Eficiencia** | No requieren un sistema operativo completo (como las VMs). Se inician en segundos y consumen menos recursos. |
            | **Escalabilidad** | Es trivial ejecutar decenas o cientos de instancias idénticas (p. ej., para balanceo de carga). |
            | **Declaratividad** | El entorno se define como código (`Dockerfile`, `docker-compose.yml`), lo que permite versionarlo, revisarlo y automatizarlo. |

            ---

            ## 🆚 Contenedores vs Máquinas Virtuales (VMs)

            | Característica | Máquina Virtual | Contenedor |
            |----------------|-----------------|------------|
            | **Capa de virtualización** | Hipervisor (emula hardware) | Kernel del host (aislamiento a nivel de proceso) |
            | **Sistema operativo** | SO completo por VM (guest OS) | Comparte el kernel del host |
            | **Tamaño** | Gigabytes (SO + apps) | Megabytes (solo app + dependencias esenciales) |
            | **Tiempo de arranque** | Segundos a minutos | Milisegundos |
            | **Densidad** | Decenas por servidor | Cientos o miles por servidor |

            > 🎯 **No son rivales, sino complementarios**:  
            > En la nube, es común ejecutar **contenedores dentro de VMs** para combinar seguridad de aislamiento fuerte (VM) con eficiencia y agilidad (contenedores).

            ---

            ## 🌐 Ejemplo del mundo real

            Sin contenedores:  
            🔹 Desarrollador A usa Java 11, MySQL 8.0, Ubuntu 22.04.  
            🔹 Servidor de producción usa Java 8, MySQL 5.7, CentOS 7.  
            → La app falla por incompatibilidades silenciosas.

            Con contenedores:  
            🔹 Todos usan la **misma imagen**: `openjdk:17-jdk + app.jar + MySQL driver`.  
            🔹 El entorno es *idéntico* en todas partes.  
            → La app se comporta igual **siempre**.

            > 💡 **Conclusión**:  
            > Los contenedores no solo son una herramienta técnica — son una **filosofía de trabajo** que promueve consistencia, colaboración y entrega continua.
        
        === "Comandos escenciales"
            ## 📜 Tabla de comandos esenciales para contenedores

            | Categoría         | Comando                                      | Descripción                                                                 | Ejemplo de uso                                  |
            |-------------------|----------------------------------------------|-----------------------------------------------------------------------------|-------------------------------------------------|
            | **Crear/Ejecutar** | `docker run [OPCIONES] IMAGEN`               | Crea e inicia un nuevo contenedor a partir de una imagen.                  | `docker run -d --name web -p 8080:8080 nginx` |
            |                   | `docker run -it IMAGEN comando`              | Ejecuta un contenedor en modo interactivo (terminal).                      | `docker run -it --rm ubuntu bash`             |
            | **Listar**        | `docker ps`                                  | Muestra contenedores **en ejecución**.                                      | `docker ps`                                    |
            |                   | `docker ps -a`                               | Muestra **todos** los contenedores (incluidos detenidos).                   | `docker ps -a`                                 |
            | **Inspeccionar**  | `docker logs CONTENEDOR`                     | Muestra los logs de salida estándar del contenedor.                         | `docker logs web`                              |
            |                   | `docker logs -f CONTENEDOR`                  | Sigue los logs en tiempo real (como `tail -f`).                             | `docker logs -f db`                            |
            |                   | `docker inspect CONTENEDOR`                  | Muestra metadatos detallados en formato JSON.                               | `docker inspect web \| jq '.[0].NetworkSettings'` |
            | **Acceder**       | `docker exec -it CONTENEDOR comando`         | Ejecuta un comando dentro de un contenedor **en ejecución**.                | `docker exec -it db mysql -u root -p`         |
            | **Detener**       | `docker stop CONTENEDOR`                     | Detiene el contenedor de forma elegante (envía `SIGTERM` → `SIGKILL`).     | `docker stop web`                              |
            |                   | `docker kill CONTENEDOR`                     | Detiene el contenedor inmediatamente (`SIGKILL`).                           | `docker kill app`                              |
            | **Reiniciar**     | `docker restart CONTENEDOR`                  | Detiene y vuelve a iniciar el contenedor.                                   | `docker restart cache`                         |
            | **Eliminar**      | `docker rm CONTENEDOR`                       | Elimina un contenedor **detenido**.                                         | `docker rm old-app`                            |
            |                   | `docker rm -f CONTENEDOR`                    | Fuerza la eliminación (detiene y elimina en un paso).                       | `docker rm -f temp`                            |
            |                   | `docker container prune`                     | Elimina **todos** los contenedores detenidos.                               | `docker container prune -f`                    |
            | **Gestión masiva**| `docker stop $(docker ps -q)`                | Detiene todos los contenedores en ejecución.                                | `docker stop $(docker ps -q)`                  |
            |                   | `docker rm -f $(docker ps -aq)`              | Elimina **todos** los contenedores (en ejecución o no). ⚠️ ¡Cuidado!        | `docker rm -f $(docker ps -aq)`                |
            | **Políticas**     | `docker run --restart POLÍTICA ...`          | Define comportamiento ante fallos o reinicios del host.                     | `docker run -d --restart unless-stopped redis` |

            > 💡 **Sugerencias de uso**:
            > - Usa `--name` para asignar nombres significativos (evita IDs como `a1b2c3`).
            > - Usa `-d` para servicios (web, DB); `-it` para sesiones interactivas.
            > - Usa `--rm` con `-it` en contenedores temporales para limpieza automática.
            > - Siempre verifica con `docker ps -a` antes de eliminar.

        === "Ciclo de Vida"
            ## 🧊 Gestión del Ciclo de Vida de Contenedores

            Un contenedor no es estático: nace, vive, se detiene, se reinicia y finalmente muere. Dominar su ciclo de vida es esencial para usar Docker de forma eficiente y segura.

            > 🔑 **Principios clave**:  
            > Los contenedores son **efímeros**. 

            > Diseña tus aplicaciones asumiendo que cualquier contenedor puede desaparecer en cualquier momento. 

            >La persistencia debe manejarse **fuera** del contenedor (volúmenes, servicios externos).

            ---

            ### 🚀 1. Crear y ejecutar contenedores

            El comando `docker run` **crea + inicia** un contenedor en un solo paso.

            ### Sintaxis básica
            ```bash
            docker run [OPCIONES] IMAGEN [COMANDO] [ARGUMENTOS]
            ```
            ### 🚀 2. Modos de ejecución: ¿interactivo o en segundo plano?

            ▶️ Ejecución interactiva (-it)

            Ideal para shells, depuración o apps CLI.

            ### 🔧 Flags para modo interactivo

            | Flag | Nombre largo         | Significado                                                                 | Cuándo usarlo                                                                 |
            |------|----------------------|-----------------------------------------------------------------------------|-------------------------------------------------------------------------------|
            | `-i` | `--interactive`      | Mantiene **STDIN abierto** incluso si no está conectado a una terminal. Permite enviar entrada al proceso (ej: escribir en una shell). | Siempre que necesites interactuar con el proceso (ej: introducir contraseñas, comandos). |
            | `-t` | `--tty`              | Asigna una **pseudo-terminal (TTY)**. Habilita formato, colores, autocompletado y control de cursor (como una terminal real). | Cuando el proceso espera una terminal (ej: `bash`, `sh`, `mysql` CLI).        |
            | `-it`| `--interactive --tty`| **Combinación esencial** para sesiones interactivas completas.              | ✅ Casi siempre para: `docker run -it ubuntu bash`, `docker exec -it app sh` |

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


    

        


