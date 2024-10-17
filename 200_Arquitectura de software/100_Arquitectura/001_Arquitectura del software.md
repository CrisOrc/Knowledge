
# ¿Qué es la arquitectura del software?

La arquitectura de software es la planeación o estructuración del modelo, requerimientos o funcionalidades que requieren un software para suplir las necesidades o las soluciones que se requieren y para la cual fue pensada.

Según los libros lo que definen la arquitectura de software dicen lo siguiente:

Arquitectura de software: "La estructura del sistema, compuesta por elementos de software, sus propiedades visibles y sus relaciones" _Según: Software Architecture in practice (Bass, Clements & Kazman, 2003)_

"Conjunto de decisiones principales de diseño tomadas para el sistema" _Según: Software Architecture: Foundations, Theory and Practice (Taylor, 2010)_

"(...) la arquitectura se reduce a las cosas importantes, cualesquiera que sean" _Según: Patterns of Enterprise Application Architecture (Fowler, 2002)_

---

# Objetivos del arquitecto

El arquitecto requiere conectar los requerimientos del sistema y los #stakeholders
los #stakeholders son los siguientes:
- **Clientes:** Son quienes hicieron al solicitud del software, desenado que sea entregado en el tiempo establecido y que no supere el presupuesto planteado para la entrega del proyecto
- **Manager:** Es quien quiere cumplir el tiempo y los requerimientos pedidos por el cliente conformando los equipos de desarrollo que requieran para el cumplimiento del producto, se requiere tener una comunicación clara entre los equipos
- **Developer(Dev) o desarrolladores:** son las personas que programarán e implementaran el software siempre preocupados por su fácil implementación para facilitar el mantenimiento y la escalabilidad.
- **Usuario:** Son las personas que generarán una conexión con el programa, crear una confianza y facilidad en el manejo del software
- **QA o tester:** Es quien se encarga de comprobar que todos los requerimientos sean cumplidos y descubrir posibles errores o fallas en el sistema que requieran intervención para ser corregidos y mostrados al publico.


# Etapas de una arquitectura de software
Las etapas del proceso del desarrollo del software tradicionales son las siguientes 
- **Disparador:**
	- Idea o solución bajo la necesidad del producto al crear
- **[[100_Knowledge/200_Arquitectura de software/100_Arquitectura/004_Requerimientos| Análisis de requerimientos]]**
	Son todos aquellos requerimientos que necesita el software o producto para ser creado como lo son:
	- Requerimientos de negocio
	- Requerimientos del usuario 
	- Requerimientos funcionales y no funcionales
- **Diseño de soluciones** 
	Se debe analizar a profundidad el problema y su solución creando:
	- Modelos 
	- Documentación 
	- Alternativas 
	- Propuesta de valor
	- Requerimientos
- **Desarrollo y evaluación**
	Esta es la etapa de desarrollo donde se hacen implementaciones, programación y testeo generando lo siguiente:
	-  Criterios de aceptación 
	- Artefacto de software
- **Despliegue**
	Es la etapa donde se despliega el software en el se requieren los siguientes sistemas:
	- Servidores de alojamiento 
	- Estructura de ejecución 
	- Base de datos 
	- Servicios en la nube
- **Mantenimiento y evolución**
	Se detectan errores y posibles funcionamientos extras que sean necesarios, se mantiene esta etapa hasta que el software no lo requiera y en esta etapa entra en un modo de _deprecated._
# Dificultades 
## Dificultades esenciales
Todo producto contiene ciertas dificultades en las cuales hay que tener en cuenta todo momento para planificar y crear el producto como lo son: 
- **Complejidad**
	Es la dificultad que comprende el proyecto como lo puede ser la cantidad de servicios o la tecnología disponible actualmente.
- **Conformidad**
	Es el contexto del uso, como el uso de internet, que servicios debe tener, comunicaciónes
- **Tolerancia al cambio**
	Que tanto puede aaptarse o manteniendo en el tiempo, que tanta adaptación puede tener el un futuro o cambio de datos.
- **Invisibilidades**
	Es la visibilidad del proyecto, que forma va a tener, que momento puede usarse y el medio del uso .

### Solucionar las dificultades esenciales
La forma de solucionar las dificultades esenciales se puede hacer de la siguiente manera:
- **No desarrollar**
	Comprar o utilizar softwares que ya resolvieron el problema o hacer integraciones de servicios y soluciones pequeñas para crear el problema completo.
- **Prototipado rápido**
	Metodologías rápidos, generar un feedback a cada paso pequeño para saber y monitorear el camino o el proceso del desarrollo para la toma de decisiones .
- **Desarrollo evolutivo**
	Desarrollar a partir de productos o soluciones pequeñas para luego ir incrementando a medida que se avanza.
- **Grandes diseños**
	Generar soluciones creativas solo en los lugares que sean necesarios en los cuales lo requieran y sea hiperactivo aplicar.

##  Dificultades accidentales
- **Lenguajes de alto nivel**
	Es el uso de lenguajes para el cual debe usarse y programarse en el cual sea adecuado ante el contexto
- **Entornos de programación**
	Es el entorno de ejecución donde se establece el código o donde se codifica para se monitoreado
- **Multiprocesamiento**
	Son las tareas o servicios que ejecuta el producto al tiempo para su correcto funcionamiento

# Roles
Los roles en cada desarrollo que son esenciales
- **Experto del dominio:** El experto del dominio son los stakeholder, son las personas que sabe o tiene los requerimientos del producto
- **Analista:** Es la persona que indaga en que resolver, definiendo problemas o requerimientos del servicio, puede ser también el dueño del producto el cual conoce las necesidades del producto
- **Administrador de sistemas:**  Es quien hace pruebas por medio de operaciones buscando errores o problemas en el sistema o producto creado, también puede ser parte del equipo de desarrollo
- **Equipo de desarrollo:** Es el encargado de programar, hacer testing, crear la arquitectura, implementar servicios o cualquiera que esté dentro del equipo de desarrollo
- **Gestor del proyecto:** Es el facilitador, quien lidera o controla las fechas, entregas y el proceso actual para la toma de las desiciones
