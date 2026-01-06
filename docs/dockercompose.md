#  **Docker Compose**  🧩
*Para cuando una sola caja ya no basta*

🎯 **Objetivo**: Entender qué es Docker Compose, por qué es necesario, y cómo usarlo para levantar aplicaciones con múltiples servicios (ej: frontend + backend + base de datos) **en un solo comando**.  

👩‍🏫 **Enfoque**: Partimos de un problema real → introducimos la solución → construimos juntos.

---

=== "¿Por qué necesitamos Docker Compose?"

    Imagina tu aplicación moderna:

    - Un **frontend** en React (puerto 3000)  
    - Un **backend** en Node.js (puerto 5000)  
    - Una **base de datos** PostgreSQL (puerto 5432)

    ✅ Con Docker solo, podrías hacer:

    ```bash
    docker run -d --name db postgres
    docker run -d --name backend -p 5000:5000 mi-backend
    docker run -d --name frontend -p 3000:3000 mi-frontend
    ```

    Pero…

    ❓¿Cómo hacen para comunicarse? (el backend necesita hablar con la DB)

    ❓¿Qué pasa si cambias el nombre del contenedor db a database? ¡Rompe todo!

    ❓¿Y si quieres detener y borrar todo al terminar? Tres comandos más…

    Esto se vuelve frágil y repetitivo.

    💡 La solución: **Docker Compose**

    ✅Define y ejecuta aplicaciones multi-contenedor con un solo archivo YAML (docker-compose.yml).

    ✅Gestiona redes, volúmenes y dependencias automáticamente.

    ✅Un solo comando: docker compose up ➝ ¡todo listo!

    >📦 Analogía:
    >Si Docker es una caja de envío…
    >Docker Compose es el manifiesto del barco: dice cuántas cajas hay, cómo se conectan y qué necesita cada una.

=== "¿Qué es el archivo docker-compose.yml?"
    Es un archivo de configuración en formato YAML (legible por humanos) que describe:

    Los servicios (contenedores) que forman tu app.
    Sus dependencias, puertos, volúmenes, variables de entorno, etc.

    Estructura básica:

    ```bash
    
    version: "3.8"               # Versión del formato (usa 3.8 o 4 para nuevos proyectos)

    services:                    # 👉 Aquí van tus contenedores
    nombre-servicio-1:
        image: nombre/imagen
        ports:
        - "host:contenedor"
        environment:
        - CLAVE=valor
        volumes:
        - nombre-volumen:/ruta/en/contenedor
        depends_on:
        - otro-servicio

    nombre-servicio-2:
        # ... configuración ...

    volumes:                    # 👉 Volúmenes definidos (opcional, pero recomendado)
    nombre-volumen:
    ```

    ⚠️ Importante:

    > Los nombres de servicios (db, backend) se convierten en nombres DNS dentro de la red de Compose.
    > Ej: desde el backend, puedes conectar a la DB con host: db, no localhost.