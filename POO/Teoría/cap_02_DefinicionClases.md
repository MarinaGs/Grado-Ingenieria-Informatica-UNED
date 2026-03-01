# Capítulo 2: Definiciones de Clases

Este capítulo analiza el código fuente de Java mediante el proyecto `ticket-machine`, evolucionando desde una versión básica ("ingenua") hasta una funcional.

## 1. Conceptos Fundamentales
* **Campos (Fields):** Almacenan datos de forma permanente en el objeto. Definen el **estado**.
* **Constructores:** Inicializan el objeto. Se ejecutan una sola vez al crear la instancia.
* **Métodos:** Definen el **comportamiento**.
* **Encapsulamiento:** Uso de `private` para que los datos solo sean manipulables a través de métodos de la propia clase.

## 2. Elementos de la Clase en Detalle

### Campos y Tipos
Los campos se declaran al principio de la clase.
* **Tipos de datos:** Se introduce `int` para números enteros.
* **Variables de instancia:** Cada objeto tiene su propia copia de los campos.

### Constructores y Parámetros
* El constructor tiene el **mismo nombre que la clase**.
* **Parámetros:** Se usan para pasar valores desde el exterior (ej. el precio del billete al instalar la máquina).
* **Asignación:** El operador `=` mueve el valor del parámetro al campo de la clase.



### Métodos: Selectores y Mutadores
* **Métodos Selectores (Accessors):** Llevan la instrucción `return`. Su tipo de retorno coincide con el tipo del campo (ej. `public int getPrice()`).
* **Métodos Mutadores (Mutators):** Cambian el estado. No devuelven valor, por lo que usan `void` (ej. `public void insertMoney(int amount)`).

## 3. Lógica y Estructuras de Control

### Instrucciones Condicionales (`if-else`)
Es la base para que la máquina tome decisiones.
* **Forma:** `if (condición) { ... } else { ... }`.
* Permite evitar errores, como insertar cantidades negativas o imprimir billetes sin saldo suficiente.

### Operadores Relacionales
Se utilizan dentro de los `if`:
* `==` (Igual a)
* `!=` (Distinto de)
* `<` , `>` , `<=` , `>=`

### Operadores Aritméticos y Compuestos
* Operaciones básicas: `+`, `-`, `*`, `/`.
* **Asignación compuesta:** `balance += amount;` (equivale a `balance = balance + amount;`).

## 4. Salida de Datos y Cadenas
* **System.out.println:** Envía texto a la consola.
* **Concatenación:** Uso del operador `+` para unir texto y valores de variables (ej. `"Precio: " + price`).
* **Cadenas (Strings):** Texto encerrado entre comillas dobles `" "`.

## 5. Variables Locales
A diferencia de los campos:
* Se declaran **dentro** de un método.
* Son temporales: se crean al empezar el método y se destruyen al terminar.
* No tienen visibilidad fuera del método.

## 6. Caso Práctico: El Método `refundBalance`
Muestra cómo devolver el dinero:
1. Se guarda el balance en una **variable local**.
2. Se pone el balance a cero.
3. Se devuelve el valor de la variable local.

---
*Resumen exhaustivo del Tema 2 - Programación Orientada a Objetos (Grado Informática).*
