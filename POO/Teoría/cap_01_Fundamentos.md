# Capítulo 1: Objetos y Clases

Este documento detalla los conceptos fundamentales de la Programación Orientada a Objetos (POO) basados en la bibliografía oficial.

## 1. El Paradigma de Objetos
La programación orientada a objetos consiste en crear un **modelo informático** de una parte del mundo (el "dominio del problema"). Los componentes de este modelo son los objetos.

## 2. Clases y Objetos (Instancias)
* **Clase:** Es el concepto abstracto. Actúa como una plantilla o "plano" que define qué datos tendrá un objeto y qué podrá hacer. No existe como entidad física en la memoria hasta que se instancia.
* **Objeto (Instancia):** Es la entidad concreta creada a partir de una clase. Se pueden crear infinitos objetos de una misma clase, y cada uno tiene su propia identidad.

## 3. Comunicación con Objetos: Métodos y Parámetros
* **Métodos:** Representan el **comportamiento** del objeto. Son las operaciones que podemos invocar para que el objeto realice una acción.
* **Parámetros:** Son los valores de entrada que algunos métodos necesitan. 
    * Un método puede tener varios parámetros.
    * Cada parámetro tiene un **tipo** y un **nombre**.
* **Signatura:** Es la definición de la cabecera del método. Ejemplo: `void moveHorizontal(int distance)`. Indica qué recibe y qué devuelve.

## 4. El Estado de los Objetos
* **Campos (Atributos):** Son variables definidas en la clase che almacenan los datos de cada objeto.
* **Estado:** Es el conjunto de valores almacenados en todos los campos de un objeto en un momento dado. 
    * *Nota:* El estado de un objeto puede cambiar a lo largo del tiempo mediante la ejecución de métodos.

## 5. Tipos de Datos
En Java, los parámetros y campos deben tener un tipo definido:
* **Tipos Primitivos:** Como `int` (enteros) o `boolean` (lógicos: true/false).
* **Tipos de Objeto:** Como `String` (cadenas de texto, siempre con comillas dobles `" "`).

## 6. Aspectos Técnicos de Java
* **Código Fuente:** Es el texto escrito en lenguaje Java que define la clase.
* **Compilador:** Es la herramienta que traduce el código fuente (comprensible por humanos) a un formato que la máquina puede ejecutar. Si hay errores de sintaxis, la compilación fallará.
* **Code Pad (Banco de pruebas):** Herramienta interactiva para ejecutar líneas de código Java directamente sin necesidad de escribir una clase completa, útil para probar la interacción entre objetos.
* **Notación de punto:** Sintaxis estándar para invocar métodos: `objeto.metodo(valor)`.

## 7. Conceptos clave para recordar
- **Abstracción:** Ignorar detalles irrelevantes para concentrarse en lo importante del objeto.
- **Interacción:** Los objetos pueden comunicarse entre sí invocando métodos de otros objetos (como se ve en el ejemplo del proyecto `house`).
