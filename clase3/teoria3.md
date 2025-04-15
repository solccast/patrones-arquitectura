# Patrones de arquitectura - Clase 3 - 2025

## Documentacion de la arquitectura
Vincula la implementación del sistema con el modelo de arquitectura. Se lo trata como un esqueleto que que se usa por todos los miembros del equipo.

### C4 Model
> Menor exigencia formal que el UML: más orientado a los stakeholders. 

Proporciona una forma estructuradad y escalable para describir y comunicar la arquitectura de software a diferentes audiencias. 

El modelo C4 se basa en cuatro niveles de abstracción, cada uno de los cuales proporciona una vista diferente del sistema: 
- Contexto: proporciona una vista de alto nivel de la arquitectura. Ejemplo: cliente pegando a un servicio web y le devuelve el resultado. 
- Contenedor: describe la estructura y la interacción de los contenedores que forma la aplicación. Ejemplo: tiene un frontend, un backend y una base de datos.
- Componente: describe la estructura interna de cada contenedor. Ejemplo: el frontend tiene un componente de login, otro de registro y otro de dashboard.
- Código. 

## The Twelve-Factor App

> Un conjunto de principios para construir aplicaciones modernas en la nube. 

> El objetivo es minimizar la distancia entre el entorno de desarrollo y producción que facilitan la integración continua. 

1. Codebase: una única base de código gestionada con control de versiones, utilizando tags o branches para las diferentes versiones. 

2. Dependencias: declarar y aislar las dependencias. No debepende de la existencia explícita de paquetes instalados en el sistema. 

3. Configuración: ninguna referencia a puertos o credenciales en el código. Se deben usar archivos de configuración o variables de entorno.

4. Backing services: tratar los servicios externos como recursos adjuntos, configurandolos de manera simiular a la configuración. 

5. Build, release, run: separar la etapa de construcción de la etapa de ejecución. 
   - Build: se traen las dependencias y se compilan los binarios usando una versión concreta del código. 
   - Release: se usa la imagen de Docker o el binario compilado y se le inyecta la configuración.
    - Run: se ejecuta el binario o la imagen de Docker. Lanzar los procesos. 

6. Processes: ejecutar la aplicación como uno o más procesos sin estado (sin guardar estado en memoria ni la sesión) para facilitar la replicación y la escalabilidad horizontal.

7. Port binding: publicar servicios mediante asignación de puertos. Las aplicaciones son completamente auto-contenidas e independientes de servidores web específicos. 

8. Concurrencia: escalar horizontalmente mediante el modelo de procesos sin estado. Se pueden tener múltiples instancias del mismo servicio ejecutándose concurrentemente.

9. Desechabilidad (req. no funcional): diseñar los servicios para que se inicien y finalicen rápidamente y de forma segura. 

10. Igualdad entre desarrollo y producción: Mantener la mayor igualdad posible entre los entornos de desarrollo, staging y producción para facilitar despliegue continuo y reducir riesgos (hacer cosas más chicas y pongan rápido a producción).

11. Logs: tratar los logs como flujos de eventos. No deben preocuparse por el direccionamiento o almacenamiento de logs sino escribirlos en la salida estándar.

12. Administración de procesos: ejecutar las tareas de gestión/administración como procesos que solo se ejecutan una vez. 




