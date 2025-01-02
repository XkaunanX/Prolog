# Prolog

Prolog es un lenguaje de programacion basado en logica, utilizado principalmente para resolver problemas relacionados con la inteligencia artificial y la manipulacion de conocimiento. Su nombre proviene de "Programming in Logic" (Programacion en Logica). A diferencia de otros lenguajes, Prolog se enfoca en la declaracion de hechos y reglas que describen relaciones entre objetos y permite deducir respuestas mediante un proceso automatizado.

## En que contexto nacio Prolog

Prolog fue desarrollado en la decada de 1970 por Alain Colmerauer y Philippe Roussel en la Universidad de Aix-Marseille, como parte de un proyecto de investigacion en inteligencia artificial. El objetivo era crear un lenguaje que pudiera representar y manipular conocimiento de manera declarativa. Desde su creacion, Prolog ha sido utilizado en aplicaciones de procesamiento de lenguaje natural, sistemas expertos, y razonamiento automatico.

## Caracteristicas Principales

- **Bajo o Alto Nivel**: Prolog es un lenguaje de alto nivel, diseñado para facilitar la expresion de problemas en terminos logicos, sin necesidad de especificar los detalles de como se deben realizar los calculos o manipulaciones de datos.

  **Ejemplo**: 
  En lugar de escribir instrucciones detalladas para recorrer una lista y realizar operaciones, en Prolog simplemente se define la relacion entre los elementos y el motor de inferencia se encarga del resto.

- **Uso de Punteros**: En Prolog, no se utilizan punteros explicitamente como en lenguajes de bajo nivel. Sin embargo, la gestion de memoria y las relaciones entre hechos y reglas se manejan de manera automatica a traves del motor de inferencia, que permite la busqueda de soluciones a los problemas planteados.

  **Ejemplo**: 
  Prolog maneja internamente la memoria para gestionar los hechos y las variables de manera eficiente sin que el programador deba preocuparse por punteros o gestion de memoria manual.

- **Paradigma Logico**: El paradigma logico es el enfoque principal de Prolog, lo que significa que los programas son descritos como un conjunto de hechos y reglas logicas, y el motor de inferencia trata de encontrar soluciones que satisfagan estas relaciones.

  **Ejemplo**:
  - Hechos: `padre(juan, maria).` (Juan es padre de Maria).
  - Regla: `abuelo(X, Y) :- padre(X, Z), padre(Z, Y).` (X es abuelo de Y si X es padre de Z y Z es padre de Y).

  **Características del paradigma lógico**:
  - Declarativo: El programador define "qué" se desea lograr, no "cómo" hacerlo.

    **Ejemplo**: 
    En lugar de especificar paso a paso como recorrer una lista y sumar los elementos, en Prolog simplemente declaramos una relación y el motor de inferencia encuentra la solución.

  - Inferencia: El sistema deduce respuestas a partir de las reglas y hechos proporcionados.

    **Ejemplo**: 
    Si se tiene el hecho `padre(juan, maria).` y la regla `abuelo(X, Y) :- padre(X, Z), padre(Z, Y).`, el sistema puede inferir que Juan es abuelo de los hijos de Maria si existen tales hechos.

  - Backtracking: Si el sistema no encuentra una solución en el primer intento, retrocede y prueba con diferentes combinaciones de hechos y reglas.

    **Ejemplo**: 
    Si se consulta `abuelo(juan, X).`, Prolog tratara de encontrar un valor para X mediante backtracking, probando diferentes posibilidades hasta encontrar una solución.

  - Unificación: Se utiliza para comparar términos y determinar si pueden ser considerados equivalentes en un contexto dado.

    **Ejemplo**: 
    Si tenemos la consulta `padre(juan, X)` y el hecho `padre(juan, maria)`, la unificación asigna a X el valor `maria`, ya que los términos coinciden.

- **Tipo de Tipado**: Prolog es un lenguaje de tipado dinamico, lo que significa que los tipos de las variables no se especifican de manera explicita, sino que son inferidos por el sistema en tiempo de ejecucion. Los términos pueden representar variables, constantes, listas, y otros tipos de datos que se manipulan de manera flexible durante la ejecución.

  **Ejemplo**: 
  Si declaramos `padre(juan, maria).`, el sistema infiere que `juan` y `maria` son términos de tipo "entidad" o "persona", sin necesidad de especificar su tipo explicitamente.

## Base de Conocimientos

En Prolog, el conocimiento se representa mediante hechos y reglas, los cuales conforman la base de conocimientos de un programa.

### Hechos
Son afirmaciones que describen relaciones entre objetos. Se utilizan para establecer las propiedades de los elementos dentro del dominio del problema.

  **Ejemplo**: 
  `padre(juan, maria).` (Juan es padre de Maria).

### Reglas
Las reglas permiten establecer relaciones más complejas entre hechos y permiten inferir nuevos hechos a partir de otros existentes.

  **Ejemplo**: 
  `abuelo(X, Y) :- padre(X, Z), padre(Z, Y).` (X es abuelo de Y si X es padre de Z y Z es padre de Y).

### Motor de Inferencias
Es el componente de Prolog que maneja la búsqueda de soluciones a partir de la base de conocimientos. Utiliza el mecanismo de inferencia para derivar respuestas.

  **Ejemplo**: 
  Si se consulta `abuelo(juan, X).`, el motor de inferencias buscara un valor para X que satisfaga la regla definida anteriormente.

### Backtracking
El backtracking es una técnica utilizada en Prolog para explorar posibles soluciones a un problema. Si una rama de la búsqueda no lleva a una solución, el motor de inferencia retrocede y prueba otra posibilidad.

  **Ejemplo**: 
  Si se consulta `padre(X, Y).` y hay varios hechos como `padre(juan, maria).` y `padre(juan, jose).`, Prolog probará cada uno de estos hechos en orden, retrocediendo si no encuentra una solución.

### Unificación
La unificación es un proceso que compara dos términos y determina si pueden ser igualados mediante una serie de sustituciones de variables. Esto es fundamental para el razonamiento y la deducción en Prolog, ya que permite que las reglas se apliquen a los hechos de manera eficiente.

  **Ejemplo**: 
  Si tenemos el hecho `padre(juan, maria).` y la consulta `padre(X, Y)`, Prolog unificará `X` con `juan` y `Y` con `maria`.
