# **Arquitectura de software**

La arquitectura de software es la estructura fundamental de un sistema, formada por sus componentes principales, las relaciones entre ellos y las decisiones de diseño que determinan cómo cumple sus requisitos funcionales y no funcionales.

##**¿Qué es la arquitectura de software?**

Imagina que vas a construir una casa 🏠.  Antes de empezar a colocar ladrillos, necesitas un **plano**: cuántas habitaciones tendrá, dónde irá la cocina, cómo se conectan los baños, por dónde entra la luz…  Ese plano es, en términos de software, la **arquitectura**.

➡️ **La arquitectura de software es el “plano” de una aplicación**:  
Define qué partes la componen (módulos o servicios), cómo se comunican entre sí, qué tecnologías se usan, y cómo se van a desplegar y mantener.

No es código, pero **guía todo el código** que vendrá después.

---

## **¿Para qué sirve?**

- ✅ **Alinear lo técnico con lo que necesita el negocio**  
  (ej: si la app debe escalar rápido, no diseñamos un monolito gigante).

- ✅ **Garantizar calidad**: que sea rápida, segura, fácil de cambiar y que no se caiga cada dos por tres.

- ✅ **Facilitar el trabajo en equipo**: todos saben cómo está estructurado el sistema, sin tener que adivinar.

- ✅ **Tomar decisiones con criterio**, no al tanteo:  
  _¿Microservicios? ¿Capas? ¿Serverless?_ → la arquitectura te ayuda a elegir lo adecuado *para tu contexto*.

---


## **Objetivos**
- Alinear la solución técnica con las necesidades del negocio.
- Asegurar calidad: rendimiento, seguridad, mantenibilidad y escalabilidad.
- Facilitar la comunicación entre interesados.
- Guiar decisiones de diseño e implementación.

## **Componentes principales**
- Componentes o módulos: unidades funcionales.
- Conectores: mecanismos de comunicación (APIs, mensajes, eventos).
- Configuración y despliegue: cómo se instala y ejecuta el sistema.
- Restricciones y decisiones arquitectónicas documentadas.



## **Impacto en la calidad**
- Influye directamente en rendimiento, disponibilidad, seguridad y coste de mantenimiento.
- Decisiones tempranas tienen efecto a largo plazo; cambios posteriores pueden ser costosos.

## **Buenas prácticas**
- Documentar decisiones arquitectónicas (ADR).
- Definir límites claros entre componentes.
- Priorizar requisitos no funcionales relevantes.
- Adoptar patrones cohesionados con el contexto del proyecto.
- Automatizar tests y despliegues.

---
<iframe width="560" height="315" src="https://www.youtube.com/embed/XrjY2iOVR8o?si=Jl95Z-S4K18Bl4Yn" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


???+ info "1.1 Estilos arquitectónicos de software"
    === "Arquitectura monolítica"
        === "**Definición**" 
            Aplicación construida como una única unidad de código, donde frontend, backend y base de datos están fuertemente acoplados.
        === "**Ventajas**"
            - Fácil de desarrollar, probar y desplegar inicialmente.
            - Ideal para aplicaciones pequeñas o MVPs.
        === "**Limitaciones**"
            - Difícil de escalar horizontalmente.
            - Cambios en un módulo requieren reconstruir y redeploy todo el sistema.
            - Riesgo alto: un fallo puede caer toda la aplicación.

        ![Arquitectura Monolitica](https://aprenderbigdata.com/wp-content/uploads/arquitectura-monolitica.jpg.webp)

          📌 **Ejemplo común**: WordPress, sistemas ERP tradicionales.
          https://aprenderbigdata.com/wp-content/uploads/arquitectura-monolitica.jpg.webp

          🔗 [Más sobre arquitectura monolítica – Martin Fowler](https://martinfowler.com/bliki/MonolithFirst.html)
        
          <iframe width="560" height="315" src="https://www.youtube.com/embed/JK-i8DBVgyY?si=VDp0ynXMOwCTF8m8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

          🖼️ *Ilustración sugerida*: Diagrama de una aplicación monolítica con capas (UI, Lógica, Datos) dentro de un solo bloque.

    === "Microservicios"
        === "**Definición**" 
            -  Arquitectura donde una aplicación se divide en servicios pequeños, independientes y especializados.
        === "**Principios clave**"
            - **Autonomía**: Cada servicio se desarrolla, despliega y escala por separado.
            - **Datos por servicio**: Cada microservicio tiene su propia base de datos.
            - **Comunicación**: REST, gRPC o mensajería (Kafka, RabbitMQ).
        === "**Patrones comunes**"
            - **API Gateway**: Único punto de entrada para clientes.
            - **Circuit Breaker**: Evita cascadas de fallos.
            - **Service Discovery**: Encuentra servicios dinámicamente.
            - **Config Server**: Gestión centralizada de configuraciones.
        === "**Desafíos**"
            - Complejidad operacional.
            - Monitoreo distribuido.
            - Consistencia eventual.
        
        ![Arquitectura Microservicios](https://cdn.prod.website-files.com/64ac7c50a66fc969e9042373/64ad79579067ac30b4d4915e_5f4fe36cf0f9e070fca4fc78_Arquitetura2.png)

        📌 **Casos de uso**: Netflix, Amazon, Rappi.

        🔗 [Microservices.io – Martin Fowler](https://microservices.io/)
        🔗 [Patrones de microservicios – Microsoft](https://learn.microsoft.com/en-us/azure/architecture/microservices/)

        🖼️ *Ilustración sugerida*: Múltiples servicios (Usuarios, Pedidos, Pagos) comunicándose entre sí y con un API Gateway.


    === "Arquitectura hexagonal (Puertos y Adaptadores)"

    

        === "**Definición**"
            Patrón de diseño que separa la lógica de negocio central ("core") de los detalles tecnológicos externos (UI, bases de datos, APIs).
        === "**Principios**"
            - El núcleo no depende de frameworks ni infraestructura.
            - Las interacciones entran y salen por "puertos".
            - Los "adaptadores" traducen entre el mundo externo y el core.
        === "**Beneficios**"
            - Alta testabilidad (la lógica de negocio se prueba sin UI o DB).
            - Flexibilidad: puedes cambiar la base de datos o el frontend sin tocar el core.

        === "**Uso recomendado**"
            - Sistemas con lógica de negocio compleja (finanzas, logística).

        ![Arquitectura Hexagonal](https://raulpadilladelgado.github.io/blog/p/arquitectura-hexagonal/images/img.png)

        🔗 [Arquitectura Hexagonal – Platzi](https://platzi.com/blog/arquitectura-hexagonal/)

        🔗 [Explicación visual – YouTube: "Clean Architecture"](https://www.youtube.com/watch?v=VLhdDYaW-uI)

        

        <iframe width="560" height="315" src="https://www.youtube.com/embed/VLhdDYaW-uI?si=r8gA1pzriwIy0jRN" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

      

    === "Cliente-Servidor"
        === "**Definición**"
            Modelo distribuido donde múltiples clientes solicitan servicios a uno o más servidores centrales.
        === "**Componentes**"
              - **Cliente**: Interfaz de usuario (navegador, app móvil).
              - **Servidor**: Procesa solicitudes, gestiona datos y devuelve respuestas.
              - **Protocolos comunes**: HTTP, HTTPS, TCP/IP.
        === "**Ventajas**"
            - Centralización del control y datos.
            - Escalabilidad vertical sencilla.
        === "**Desafíos**"
            - Punto único de falla si no hay redundancia.
            - Latencia si el servidor está lejos geográficamente.
           
        ![Arquitectura Cliente Servidor](https://deer.dev/img/deerdev/blog/cliente-servidor-model.jpg)
        📌 **Ejemplo**: Una app web que consume una API REST.

        🔗 [Cliente-Servidor – GeeksforGeeks](https://www.geeksforgeeks.org/client-server-model/)

    === "Orientada a servicios (SOA)"
        - **Definición**: Arquitectura donde funcionalidades se exponen como servicios reutilizables a través de una red.
        - **Características**:
            - Servicios de granularidad media/gruesa.
            - Uso de ESB (*Enterprise Service Bus*) para orquestar flujos.
            - Comunicación síncrona y asíncrona.
        - **Diferencia con microservicios**: SOA es más orientada a la empresa y permite mayor acoplamiento.

        📌 **Ideal para**: Grandes organizaciones con sistemas legacy.

        🔗 [SOA vs Microservices – IBM](https://www.ibm.com/topics/soa-vs-microservices)

        🖼️ *Ilustración sugerida*: Varios servicios conectados a un bus central (ESB).

    === "Serverless (FaaS)"
        - **Definición**: Modelo donde el proveedor ejecuta fragmentos de código (funciones) en respuesta a eventos, sin gestión de servidores.
        - **Modelo**: *Pay-per-use* (pagas solo por tiempo de ejecución).
        - **Plataformas**:
            - AWS Lambda
            - Google Cloud Functions
            - Azure Functions
            - Vercel Functions
        - **Ventajas**:
            - Escalado automático.
            - Bajo costo en cargas variables.
            - Ideal para tareas event-driven (subir archivo → procesar imagen).
        - **Desafíos**:
            - *Cold start* (retraso en primera ejecución).
            - Tiempo máximo de ejecución limitado.

        🔗 [Serverless Land – AWS](https://serverlessland.com/)
        🔗 [¿Qué es Serverless? – FreeCodeCamp (YouTube)](https://www.youtube.com/watch?v=8uZZSiEWwro)

        🖼️ *Ilustración sugerida*: Evento (ej: subida de archivo) disparando una función en la nube.



## **Arquitecturas más comunes (y cuándo usarlas)**

| Estilo | ¿Qué es? | ✅ Ventajas | ⚠️ Cuándo usarlo (y cuándo no) |
|--------|-----------|-------------|-------------------------------|
| **Monolito en capas** | Todo el código vive en un solo proyecto, organizado por capas (presentación → lógica → datos). | ✔️ Fácil de entender, desarrollar y desplegar al principio.<br>✔️ Ideal para proyectos pequeños, MVPs o equipos pequeños. | ✅ **Úsalo** si estás empezando, no sabes bien los requisitos, o es un prototipo.<br>❌ **Evítalo** si ya sabes que necesitarás escalar mucho o equipos grandes trabajando en paralelo. |
| **Cliente-Servidor** | Un cliente (web, app móvil) le pide cosas a un servidor (API, base de datos). | ✔️ Separación clara de responsabilidades.<br>✔️ Muy común en apps web y móviles. | ✅ **Úsalo** casi siempre que haya una app con frontend y backend.<br>⚠️ Vigila la latencia y el punto único de falla (usa redundancia). |
| **Microservicios** | La app se divide en servicios pequeños, autónomos, cada uno con su lógica y datos. | ✔️ Equipos pequeños pueden moverse rápido.<br>✔️ Escalabilidad y tolerancia a fallos más finas.<br>✔️ Puedes usar distintas tecnologías por servicio. | ✅ **Úsalo** si ya tienes un sistema grande y complejo *y* un equipo con experiencia en DevOps, redes y testing distribuido.<br>❌ **No empieces con esto** (ver más abajo ⬇️). |
| **Arquitectura hexagonal** (Puertos y Adaptadores) | El corazón del sistema (lógica de negocio) está en el centro, y “se conecta” al mundo exterior mediante puertos (ej: base de datos, APIs, UI). | ✔️ Muy fácil de probar (puedes simular la base de datos o el frontend).<br>✔️ Cambiar tecnología es más seguro (ej: migrar de SQL a MongoDB sin tocar el core). | ✅ **Úsalo** cuando la lógica de negocio es compleja y debe durar años (ej: sistemas financieros, logística). |
| **Serverless (FaaS)** | Escribes solo funciones que se ejecutan en la nube cuando ocurre un evento (ej: subir un archivo, recibir un mensaje). | ✔️ No administras servidores.<br>✔️ Pagas solo cuando se usa.<br>✔️ Escalado automático. | ✅ **Úsalo** para tareas puntuales, asíncronas o con carga variable (procesamiento de imágenes, notificaciones, webhooks).<br>❌ No es ideal para apps con estado o que requieran ejecuciones largas. |

---

<iframe width="560" height="315" src="https://www.youtube.com/embed/HOi_Wb7SVkw?si=uU5TVqwIF_DlOL93" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## 🚨 ¡Ojo con los mitos!

- ❌ *"Microservicios siempre son mejores que un monolito"* → **Falso.**  
  Martin Fowler y muchos expertos recomiendan: **empieza con un monolito bien estructurado** → y solo pasa a microservicios *cuando realmente lo necesites* y *cuando ya sepas bien los límites del negocio*.  
  → Fuente: [Monolith First – Martin Fowler](https://martinfowler.com/bliki/MonolithFirst.html)

- ❌ *"Serverless = sin servidores"* → **No.** Los servidores existen, ¡pero los maneja el proveedor!  
  El nombre es más marketing que técnica 😅.

- ✅ **Lo ideal no es una arquitectura “perfecta”, sino una *adecuada* para tu equipo, presupuesto, tiempo y contexto.**

---