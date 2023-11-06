# Testing y debugging utilizando python

En esta ocasión se utilizará jupyter notebook

Todas las diapositivas son propiedad del curso en cuestión

## Principios del testing segun [ISTQB](https://www.istqb.org/) (International Software Testing Qualifications Board)

1. Ejecutar pruebas nos permite saber los defectos que hay.
No es posible demostrar que no hay defectos
2. Probar todas las combinaciones es imposible.
3. Hacer las pruebas lo más pronto posible para detectar errores lo mas antes.
4. Hay componentes que son más propensos a ser la causa del problema.
5. Constante revisión y actualización de las pruebas.
6. El testing es totalmente dependiente del contexto.
7. La ausencia de errores no quiere decir que sea útil para el cliente.

[Tipos de pruebas](https://es.wikipedia.org/wiki/Pruebas_de_software)

## Roles
La mayoria de las veces el equipo se conforma de los siguientes roles
* Responsable del equipo (idealmente senior)
* Desarrolaador/Programador (quién lleva los requerimientos)
* Diseñador grafico o UX
* Tester, el de calidad

## Error, defecto y fallo
* Error: Es toda falla humana que genera un desperfecto, algo incorrecto, hace referencia al programador, en el código está la solución.
* Defecto:  Es un desperfecto en el componente, en el lenguaje per se, que no lo hace como queremos.
* Fallo: La manifesración física o visual de un defecto.

## Requisito y Calidad
* Requisito: Es lo que se requiere para algo, es un atributo deseado u obligatorio
    * Funcional: Se evalúa el comportamiento o funcionabilidad del sistema
        * Correctud
        * Completud
    * No funcional: Juzga la operación, la disponibilidad, fiabilidad, seguridad
    No tiene nada que ver con la función, sino con la experiencia
        * Rendimiento
        * Estabilidad
        * Seguridad

* Calidad: Grado del componente que cumple los requisitos, es proporcional al nivel de compromiso o sociabilidad con el cliente jsjs

Van de la mano ya que la calidad es (en parte) el nivel de requerimientos que se han cumplido, el testing busca cumplir todos los requisitos.

## Modelos del desarrollo

### Cascada

5 fases bien definidas

1. Requisitos: Analisis de requisitos
2. Diseño: Diseño de la estrcutura del software, UML, UX, base de datos, etc.
3. Implementacion: La programación de los requisitos.
4. Verificación: El testing
5. Instalación y mantemiento: Se entrega al cliente y se comprueba que funcione en el entorno

#### Ventajas
* Al estar bien definido es sencillo de entender
* Ideal donde los requisitos son claros
* Documentación facilitada

#### Desventajas
* Volvemos a la fase de requisitos al agregar funciones
* No se va mostrando el producto al cliente hasta finalizar

### V

Mejora de la cascada, muestra cómo se relaciona las actividades de prueba, el analisis y diseño. Equipos pequeños. Conforme pasan las fases se hacen la pruebas de testing.

1. Requerimientos - Pruebas de aceptación (Calidad evaluada por el cliente)
2. Diseño funcional del sistema - Pruebas de sistema (Las operaciones funcionen)
3. Diseño técnico del sistema - Pruebas de componentes (Reglas y protocolos)
4. Especificación de componentes - Pruebas unitarias (Pruebas pero de los componentes de la app)

   |     ^

   |_|

#### Ventajas
* Optmización de comunicación
* Mejora calidad
* Ahorra costes

#### Desventajas
* Simple para proyectos grandes
* Poco flexible

### Espiral
Se repite cuantas veces sea necesario hasta que el proyecto termine

1. Determinar objetivos - ¿Qué se necesita que el software haga?
2. Análisis de riesgo de la fase anterior - ¿Qué tan factible es desarrollarla?
3. Desarrollar y probar - Programarla y se hacen las pruebas de las fases anteriores
4. Planificación de la siguiente iteración

#### Ventajas
* Proyectos grandes sujetos a riesgos
* Los conflictos entre el desarrollo y el diseño se evitan al estar en ciclo y repasarlos
* Se puede obtener retroalimentación del cliente en las distintas fases

#### Desventajas
* Riesgo de que se formen bucles en el proyecto y tarde más tiempo en desarrollar

### Iterativo e incremental
Supuestamente es de los más eficientes tanto en el desarrollo como en actividades
relacionadas con la informática. 
Conjunto de tareas agrupadas en pequeñas etapas repetitivas (1 - 2 semanas)
El desarrollo se hace de manera rápida en un tiempo pequeño (24 h)

1. Inicialización - Producto básico de tal manera que se pueda obtener retroalimentación del cliente
2. Iteración - Analisis, diseño e implementación de las funcionalidades
3. Lista de control - Tareas a realizar o que se realizaron para el proyecto

#### Ventajas
* Los usuarios no tienen que esperar al final para usarlo
* Se puede ver como prototipo
* Producto consistente y puntual
* Pocos riesgos

#### Desventajas
* Entrega temprana produce sistemas simples
* El cliente está involucrado en todo el proceso
* Ojito porque en veces el cliente cree que el producto está terminado pero es solo prototipo

### RAD (Rapid Application Development - Desarooollo rápido de aplicaciones)
Construcción rápida del sistema, reduciendo los tiempos de planificación y diseño. 
Compuesto por un grupo pequeño de personas. (60 - 90 días)

1. Modelado de gestión - Analisis de requisitos
2. Modelado de datos - Cómo se relacionan los componenetes con los datos
3. Modelado de procesos - Cómo se conecta con su función en la app
4. Generación de aplicaciones - Desarrollo de la app
5. Pruebas y entrega 

#### Ventajas
* Retroalimentación del cliente de manera constante
* Avances medibles
* Adaptable

#### Desventajas
* No es para proyectos grandes
* Mucha interactividad del cliente
* De preferencia desarrolladores senior 

### RUP (Rational Unified Process - Proceso unificado de racional)
Es un conjunto de metodologías que se adapta al contexto y necesidad del proyecto.

1. Inicio - Se define los objetivos y el alcance del proyecto
2. Elaboración - Se define la arquitectura del sistema
3. Construcción - Se desarrolla el software
4. Transición - Se entrega el producto al cliente

#### Ventajas
* Se adapta al proceso
* Etapas iteradas
* Lo hacen multiples equipos

#### Desventajas
?

## Fases del testing

1. Estudio

    Se analizan los requisitos del cliente, qué es lo se requiere en la app.
    Para esto es ideal que el equipo de testers formen parte del proceso de del         
    analisis de requisitos del software, para que vaya a la par con el proyecto y 
    determinar el alcance de las pruebas.

2. Diseño
3. Estrategia
4. Escritura
5. Ejecución
6. Evaluación
7. Mantenimiento


## notas mias xd
Disciplina en la ing del soft que permite detectar defectos

No se piensa al final del desarrollo, sino a la par

La ing surgió debido a la crisis del software (un desastre)

La calidad se refiere al funcionamiento, tanto que no haya errores y que 
cumpla con el funcionamiento mismo de la app (los requerimientos)

Dentro de sus objetivos se encuentran
* Encontrar defectos
* Mejorar calidad, menos errores
* Calidad para Mejores desiciones
* Evitar aumentos de costos

Podemos automatizar las pruebas realizadas de forma manual, optimiza el testing
dandonos cuenta de errores que no vimos o por tiempo