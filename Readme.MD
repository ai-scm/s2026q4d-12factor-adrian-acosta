# Assignment 2: Twelve-Factor App

## Introducción

Las Twelve-Factor App son un conjunto de buenas prácticas para desarrollar aplicaciones modernas que sean mantenibles, escalables y fáciles de desplegar. Para este trabajo seleccioné los factores **I. Código base**, **III. Configuraciones**, **IV. Servicios de respaldo** y **V. Construir, desplegar y ejecutar**, ya que considero que son fundamentales para el trabajo organizado de un equipo y para mantener una separación clara entre la aplicación y su entorno de ejecución.

## Factores seleccionados

### I. Código base

Considero este factor importante porque trabajamos como equipo y todos debemos construir y mantener sobre la misma línea de trabajo. Tener un único código base registrado en un sistema de control de versiones permite que los integrantes compartan la misma historia del proyecto, trabajen sobre ramas de manera organizada y puedan revisar e integrar los cambios antes de llevarlos a producción.

Además, una sola base de código evita que existan múltiples versiones incompatibles de la aplicación y facilita que el equipo aplique estándares comunes de desarrollo. De esta forma, los cambios se pueden rastrear, revisar y mantener de manera controlada.

### III. Configuraciones

La separación entre el código y la configuración es necesaria en cualquier proyecto que se despliegue en diferentes entornos, como desarrollo, pruebas y producción. Las configuraciones nso deben quedar incluidas directamente en el código, sino administrarse mediante variables de entorno o mecanismos externos adecuados.

En nuestro caso, por ejemplo, es necesario manejar credenciales para acceder a los servicios de AWS. Estas credenciales deben mantenerse fuera del código fuente para reducir riesgos de seguridad y permitir que la misma aplicación pueda ejecutarse con configuraciones diferentes sin modificar su implementación.

### IV. Servicios de respaldo

Los servicios de respaldo son recursos externos que utiliza la aplicación, como bases de datos, servicios de almacenamiento, sistemas de mensajería o APIs. Aunque sean proveedores externos, deben tratarse como recursos adjuntos a la aplicación y no como partes inseparablemente integradas al código.

Este factor está relacionado con las configuraciones, ya que la conexión a los servicios puede definir su ubicación o sus credenciales mediante variables de configuración. Un acoplamiento flexible permite reemplazar o cambiar un servicio de respaldo con el menor impacto posible, siempre que mantenga la interfaz y los datos esperados por la aplicación.

Por ejemplo, una aplicación podría cambiar su proveedor de almacenamiento o utilizar una configuración distinta según el entorno sin necesidad de modificar su código base.

### V. Construir, desplegar y ejecutar

Este factor establece una separación clara entre tres etapas:

1. **Construir:** convertir el código fuente en un paquete ejecutable o artefacto reproducible.
2. **Desplegar:** llevar ese artefacto a un entorno específico aplicando su configuración.
3. **Ejecutar:** iniciar la aplicación en ese entorno.

Es importante seguir estas etapas en el orden definido y utilizar un proceso estándar para realizarlas. Saltarse pasos, modificar cada despliegue de forma manual o ejecutar acciones diferentes según la persona encargada puede generar inconsistencias, errores difíciles de detectar y diferencias entre entornos.
