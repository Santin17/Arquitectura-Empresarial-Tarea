# Arquitectura-Empresarial-Tarea

# Reporte de Arquitectura: Servicios Web y Despliegue

Este documento detalla las decisiones arquitectónicas tomadas para la integración de servicios web y la automatización del ciclo de vida del software.

## 1. Documentación de la API: REST vs. SOAP

Para la comunicación de nuestros servicios distribuidos, se ha seleccionado el estilo arquitectónico **REST (Representational State Transfer)**.

### Justificación de la elección:
*   **Interoperabilidad:** A diferencia de SOAP, que es altamente rígido y depende de XML, REST utiliza estándares ligeros como **JSON**. Esto facilita la conexión con aplicaciones móviles (Android/iOS) y web modernas sin complicaciones de protocolos complejos.
*   **Rendimiento:** REST es significativamente más rápido debido a que requiere menos ancho de banda. No necesita el "overhead" de las cabeceras SOAP, lo que optimiza la latencia en redes de baja velocidad.
*   **Escalabilidad:** Al ser un protocolo *stateless* (sin estado), permite que cada petición sea independiente, facilitando el crecimiento horizontal de la infraestructura empresarial.

## 2. Integración Continua (Nuevas Tendencias)

Para cumplir con las exigencias de la ingeniería de software actual, se propone la implementación de **GitHub Actions** como herramienta de automatización.

### Estrategia de Despliegue Automático:
*   **Workflow de CI:** Cada vez que se realiza un *Pull Request* o un *Merge* a la rama principal (`main`), GitHub Actions ejecutará automáticamente una serie de pasos (jobs).
*   **Beneficios:** 
    1.  **Validación:** Se verificará que el código no tenga errores de sintaxis antes de fusionarse.
    2.  **Continuous Deployment (CD):** El servicio se desplegará automáticamente en servidores de producción (como Firebase o AWS), reduciendo errores manuales y asegurando que la versión estable esté siempre disponible.