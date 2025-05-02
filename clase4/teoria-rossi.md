# Patrones de arquitectura - Charla de Gustavo Rossi - 2025

> Referencia: [Video de YT](https://www.youtube.com/watch?v=f6VwGtpATac&ab_channel=LuisMarianoBibb%C3%B3)

El diseño de software implica un proceso constante de toma de decisiones para satisfacer objetivos (requerimientos funcionales y no funcionales) y lidiar con restricciones (técnicas, organizacionales, de equipo).
La dificultad y la necesidad de creatividad surgen cuando se enfrentan problemas nuevos que no tienen soluciones predefinidas (patrones de diseño o arquitecturales).

## Modularidad
El concepto de "módulo" ha variado significativamente en 60 años, desde procedimientos y objetos hasta servicios y microservicios.
Un sistema bien construido busca:
- **Maximizar la cohesión** (que las partes de un módulo estén fuertemente relacionadas).
- **Minimizar el acoplamiento** (dependencia entre módulos).
- **Minimizar el connascence**: "cuáles son los módulos que impactan entre sí, o sea, cuando toco un módulo, qué otros módulos tengo que tocar". Esto es un derivado del acoplamiento. Dos módulos son "connascentes" si la modificación de uno, implica que debe odificarse el otro para mantener la correctitud. 

La evolución tecnológica (redes, web, aplicaciones distribuidas) ha impulsado la necesidad de que los conceptos de modularidad y arquitectura también evolucionen en conjunto del incremento de las expecttativas de los usuarios respecto a la calidad del software.

## ¿Por qué es importante la arquitectura? 
Su importancia radica en que ayuda a lidiar con la creciente complejidad a través de la abstracción. Ayuda a prever el impacto de las decisiones de diseño en la antenibilidad y evolución del sistema. 

## Características arquitecturales
Se conoce también como _requerimientos no funcionales_ o _atributos de calidad_; hacen referencia a las "virtudes del sistema" como lo es la performance, escalabilidad, mantenibilidad, seguridad y privacidad. Éstas impactan en el diseño y suelen ser contradictorias (trade off entre características como performance y escalabilidad). 

### Clasificaciones: 
- Calidad Externa: Observable por usuarios y stakeholders (performance, escalabilidad, seguridad).
- Calidad Interna: Percepción de los desarrolladores sobre el diseño (modularidad, reusabilidad, consistencia).
- Estáticas: Evaluables antes de la puesta en producción.
- Dinámicas: Evaluables mientras el sistema está en funcionamiento (ej. usabilidad bajo carga alta).

### Meta-calidad
Son atributos que describen propiedades de los atributos de calidad en sí mismo. Por ejemplo cuan observable, cuan auditable o cuan testeable es la privacidad o la performance. 

| Interna | Externa |
| -- | -- |
| modularidad | funcionalidad |
| claridad | usabilidad|
| despliegabilidad | accesibilidad|
| consistencia de diseño | capacidad|
| reusabilidad | recuperabilidad |

## Arquitectura vs. tecnología
Es un error confundir laarquitectura con la tecnología, ésta última le da "forma" a la arquitectura pero la arquitectura no debería estar atada a las tecnologías que la forman (pues cambian rápido). Una tecnología no es la arquitectura ya que esta última es más que un conjunto de productos.

## Diseño de arquitecturas de software 
La elección de un estilo o patrón arquitectural de referencia (capas, servicios, microservicios, etc.) influye fuertemente en las decisiones de diseño posteriores. 
Hay tres tipos de problemas:
- Diseño arqtectural: definición de los elementos fundamentales de nuestro sistema
- Diseño de la interacción entre elementos (componentes, partes)
- Diseño interno de los elementos
La complejidad de cada una de estas actividades tiene una relación estrecha con el estilo de arquitectura elegida. La elección de un estilo es una decisión basada en qué atributos se quieren priorizar.

## La gran bola de barro
Se define como una estructura arquitectural común en sisteas complejos, caracterizada por un alto acoplamiento. Esta estructura a menudo resulta de construir nuevas funcionalidades sobre sistemas heredados, parcheando y añadiendo capas. Afecta directamente en la mantenibilidad. 

## Evolución de las arquitecturas 
- Una sola computadora: programas corriendo en una máquina.
- Cliente-Servidor: primer salto hacia la distribución (desktop y servidor, web browser y servidor web). Toda la aplicación en el servidor. 
- Capas: separación de la lógica (cliente, servidor de aplicación, servidor de base de datos).
- Arquitecturas Monolíticas Modulares: Sistemas con una unidad de despliegue única, pero con cierto nivel de modularidad (capas, microkernel, pipeline).
- Arquitecturas Distribuidas: Múltiples unidades de despliegue (orientadas a servicios -SOA-, orientadas a eventos, microservicios). La idea es poder reusar software. 

## Ejemplos de estilos arquitecturales
- **Microkernel**: se tienen dos tipos de componentes: _core_ y _plugins_ o _extensiones_ que añaden funcionalidad personalizada. Muy usado en arquitectura de "productos" como por ejemplo Eclipse o Moodle. La estructura original no postula de qué manera el Core System se comunica con los plugins. 
- **Layered (en capas)**: las diferentes capas se organizan en capas horizontales con responsabilidades específicas (capa de negocios, capa de presentación, capa de persistencia). Una capa no conoce detalles de la capa de abajo lo que provee la posibilidad de cabios y hacer los layers independientes. 
    - Variantes: **Capas cerradas** (la comunicación pasa por la capa inmediatamente inferior) y **capas abiertas** (permite saltarse capas).

## Cómo elegir un estilo arquitectural?
La elección es el resultado de analizar tradeoffs de características arquitecturales, consideraciones de dominio, objetivos estratégicos y el contexto.
La elección está influenciada por:
- Modas: Tendencias en la industria.
- Experiencia Propia: Experiencias pasadas con ciertos estilos.
- Tecnologías Nuevas: Herramientas que habilitan nuevos enfoques (ej. Docker y microservicios).
- Cambios en Dominios: Requerimientos específicos de nuevos dominios.
- Factores Externos: Restricciones no técnicas (costos de licencias, capacidades del equipo).
