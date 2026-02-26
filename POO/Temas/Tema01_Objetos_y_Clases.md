# Tema 1: Objetos y Clases 🚗

Este es un resumen de los conceptos fundamentales del primer capítulo del libro de Programación Orientada a Objetos (POO) de la UNED. 

## 1.1 Introducción a la POO
La Programación Orientada a Objetos es un paradigma que intenta modelar partes del mundo real mediante código. A diferencia de la programación procedural (paso a paso), aquí organizamos el software en estructuras llamadas **objetos**.

## Conceptos Clave
* **Objetos**: Son modelos computacionales de entidades que provienen del dominio de un problema (ejemplo: un auto específico en una simulación de tráfico).
* **Clases**: Es el "molde" o la categoría general. Describe de forma abstracta a todos los objetos de un mismo tipo.
* **Métodos**: Son las acciones que un objeto puede realizar (ejemplo: `acelerar()`, `frenar()`).
* **Parámetros**: Información adicional que necesitan los métodos para ejecutarse (ejemplo: cuántos km/h queremos acelerar).

## Ejemplo Práctico en Java (Sintaxis UNED)
Para este curso usamos el entorno **BlueJ**. Así se vería una clase simple:

```java
/**
 * Ejemplo de clase Auto para el Tema 1
 */
public class Auto {
    private String color;

    public Auto(String colorAuto) {
        color = colorAuto; // Constructor: Crea el objeto
    }

    public void pintar(String nuevoColor) {
        color = nuevoColor; // Método con parámetro
    }
}
