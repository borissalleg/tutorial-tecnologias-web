# **Redes en contenedores**




???+ info "Redes y Driver en  Docker"
    === "Conceptos"

        Las redes en contenedores son mecanismos de virtualización de red que permiten a los contenedores comunicarse entre sí, con el sistema host y con el mundo exterior (internet, otros servidores), manteniendo al mismo tiempo un aislamiento controlado.

        A diferencia de las máquinas virtuales (que emulan hardware de red completo), los contenedores aprovechan características del kernel de Linux — como namespaces de red, interfaces virtuales (veth), puentes (bridge) y reglas de iptables/nftables — para crear redes ligeras, seguras y programables.

        ###**¿Para qué sirven?**


        ✅  **Comunicación interna:** Que una aplicación (contenedor) acceda a su base de datos (otro contenedor) usando un nombre como db.

        ✅  **Exposición controlada:**  Que un servicio web sea accesible desde tu navegador mediante http://localhost:8080, sin exponer otros puertos.

        ✅  **Aislamiento:** Que el entorno de desarrollo no interfiera con el de pruebas, aunque estén en la misma máquina.

        ✅  **Escalabilidad:** Simular arquitecturas de microservicios donde decenas de contenedores se descubren y conectan dinámicamente.

        💡 **En esencia:** Las redes convierten a los contenedores de procesos aislados en componentes interoperables de un sistema distribuido — tal como ocurre en producción.

        === " Red en Docker"
            Una red en Docker es un objeto lógico y gestionable que define un espacio aislado de comunicación entre contenedores, permitiendo el intercambio de tráfico bajo reglas específicas de conectividad, resolución de nombres y alcance. 
            
            Cada red tiene un nombre único, una configuración (subred, gateway, opciones), y una lista de contenedores conectados. 
            
            Las redes se crean, inspeccionan, conectan y eliminan mediante comandos como `docker network create`, `docker network inspect` y `docker network rm`. Representan la capa de orquestación de la conectividad.
        
        === "Driver de red en Docker"

            Un driver de red en Docker es un mecanismo de implementación subyacente que define cómo se construye y gestiona una red, especificando el comportamiento de bajo nivel: aislamiento, enrutamiento, asignación de direcciones, resolución DNS y compatibilidad con entornos distribuidos. 
            
            Es una interfaz estándar que permite a Docker interoperar con distintas tecnologías de red (puentes, VLANs, SDN, etc.). 
            
            Los drivers son inmutables y se seleccionan al crear una red; no pueden cambiarse después.







    === "Red bridge en Docker"
         **_El puente privado entre contenedores_**

        La red de tipo bridge es el mecanismo predeterminado que Docker usa para permitir la comunicación entre contenedores y con el exterior. 
        
        Su nombre viene del concepto de puente de red (network bridge) en Linux: un dispositivo virtual que conecta múltiples interfaces de red en una sola red de capa 2 (como un switch físico).

        **Analogía física**

        **_Imagina:_**

            - Tu máquina host (Windows, Linux, WSL2) es una ciudad.
            - Cada contenedor es un edificio.
            - La red bridge es una red vial privada dentro de la ciudad:
            - Los edificios (contenedores) pueden comunicarse entre sí por calles internas (por nombre o IP).
            - Para salir a la "carretera principal" (internet o tu navegador), necesitan un acceso controlado (publicación de puertos con -p).
            - Un edificio no puede ver los de otra red privada (otra red bridge personalizada).

