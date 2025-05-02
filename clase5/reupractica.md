# Reunión de Práctica 28-04-2025

> Referencia: [Video de Youtube](https://www.youtube.com/watch?v=7JXtfu4Rpco)

## Control de versiones
Es necesario una forma de nomenclar las versiones del sistema.
En la clase lo que usaremos será **versionado semántico**: `X.Y.Z` donde 
▪ X (Major): Incrementa ante modificaciones mayores que rompen la compatibilidad con versiones anteriores.
▪ Y (Minor): Incrementa ante la introducción de nueva funcionalidad que mantiene la retrocompatibilidad.
▪ Z (Patch): Incrementa ante la corrección de errores (bugs) o parches menores.

## Estrategias de ramificación
La ramificación facilita la colaboración, permite resolver conflictos, agiliza la productividad, ayuda a organizar equipos y reduce la probabilidad de tener código frágil en producción. Permite hacer seguimiento de cambios y detectar qué commits introdujeron errores.
**Consideraciones para elegir la estrategia**: tamaño del equipo (más grande, más complejo y más necesaria una estrategia clara), interacción y madurez colaborativa del equipo, complejidad del proyecto (cantidad y tamaño de requerimientos), testing y estabilidad (requerimientos no funcionales de cobertura de tests), trazabilidad deseada de los cambios, y frecuencia de los despliegues.

## Integreación continua (GitLab CI)
### Pipelines 
Es una herramienta de automatización en el proceso de construcción, prueba, integración y despliegue de un proyecto de software para garantizar su calidad y eficiencia en su ciclo de vida. 
Se configura con el archivo `.gitlab-ci.yml` en la raíz del repositorio. Define los pasos "stages" y las tareas "jobs" que se ejecutarán, a partir de diferentes eventos como commits, merges, etc. 
Consideraciones:  
- Todo push sobre main debería tener asociado un tag.
- Todo push/merge sobre main debería correr previamente los tests.

## Conventional Commits

Es una convención para el formato de los mensajes de commit. Busca mejorar la legibilidad del historial de commits.
Permite indicar el tipo de cambio (ej: `feat` para nueva funcionalidad, `fix` para corrección de bug, `breaking change` para cambio que rompe compatibilidad).
La principal ventaja es que permite la generación automática de "changelogs" (registros de cambios) o documentación de release. Esto simplifica la documentación de lo que se va desarrollando.

