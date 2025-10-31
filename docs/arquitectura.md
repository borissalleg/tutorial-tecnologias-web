# Arquitectura de software

La arquitectura de software es la estructura fundamental de un sistema, formada por sus componentes principales, las relaciones entre ellos y las decisiones de diseño que determinan cómo cumple sus requisitos funcionales y no funcionales.

## Objetivos
- Alinear la solución técnica con las necesidades del negocio.
- Asegurar calidad: rendimiento, seguridad, mantenibilidad y escalabilidad.
- Facilitar la comunicación entre interesados.
- Guiar decisiones de diseño e implementación.

## Componentes principales
- Componentes o módulos: unidades funcionales.
- Conectores: mecanismos de comunicación (APIs, mensajes, eventos).
- Configuración y despliegue: cómo se instala y ejecuta el sistema.
- Restricciones y decisiones arquitectónicas documentadas.

## Patrones y estilos comunes
- Monolito en capas (layered).
- Cliente‑servidor.
- Microservicios.
- Event‑driven / basado en mensajes.
- Arquitectura hexagonal (ports and adapters).

## Impacto en la calidad
- Influye directamente en rendimiento, disponibilidad, seguridad y coste de mantenimiento.
- Decisiones tempranas tienen efecto a largo plazo; cambios posteriores pueden ser costosos.

## Buenas prácticas
- Documentar decisiones arquitectónicas (ADR).
- Definir límites claros entre componentes.
- Priorizar requisitos no funcionales relevantes.
- Adoptar patrones cohesionados con el contexto del proyecto.
- Automatizar tests y despliegues.

## Ejemplo breve
- Sistema web: interfaz (frontend) ↔ API REST (backend) ↔ base de datos; puede evolucionar hacia microservicios para escalar dominios independientes.
