# 📚 Apuntes de POO - Capítulo 1: Objetos y Clases

## 1. El Concepto de Modelo
Programar en POO consiste en crear un **modelo computacional** de partes del mundo real basándose en los objetos que aparecen en el dominio del problema.

## 2. Clases y Objetos (Instancias)
La diferencia fundamental es la generalidad vs. la particularidad:

* **Clase**: Es la categoría o "molde" abstracto. Describe qué datos y acciones tendrán los objetos de ese tipo (Ej: La clase `Auto` o la clase `Circulo`).
* **Objeto (Instancia)**: Es un caso individual y concreto creado a partir de una clase. Tiene datos específicos (Ej: "Mi auto rojo" o `circulo1`).


## 3. Métodos y Parámetros
Son la forma en que interactuamos con los objetos:

* **Métodos**: Son las operaciones o acciones que un objeto puede realizar (Ej: `moverDerecha`, `cambiarColor`). Se dice que un método se **invoca** o se llama.
* **Parámetros**: Es la información adicional que algunos métodos necesitan para trabajar (Ej: ¿cuántos píxeles mover el círculo?).
* **Signatura**: Es el encabezado del método que indica su nombre y qué parámetros recibe (Ej: `void moverHorizontal(int distancia)`).

## 4. El Estado de un Objeto
El **Estado** es el conjunto de valores de todos los atributos (o campos) que definen a un objeto en un momento dado.
* **Campos (Fields)**: Son las variables donde el objeto guarda sus datos (ej: `diametro`, `posicionX`, `color`).
* Todos los objetos de una misma clase tienen los mismos campos, pero sus **valores** pueden ser diferentes.
