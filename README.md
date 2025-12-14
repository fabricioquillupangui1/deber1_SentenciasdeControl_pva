# 📘 Control de Flujo: Sentencias de Control en Kotlin y Android Compose

## 🚀 Visión General del Proyecto

Este repositorio documenta y proporciona ejemplos funcionales de las estructuras de **Control de Flujo (Sentencias de Control)** en el lenguaje Kotlin, aplicadas al desarrollo de la interfaz de usuario con **Jetpack Compose**.

El objetivo es demostrar cómo las decisiones (`if`, `when`), las repeticiones (`for`, `while`) y el manejo de excepciones (`try/catch`) son fundamentales para construir la lógica y la interactividad de una aplicación Android moderna.

---

## ✨ ¿Qué son las Sentencias de Control?

Las sentencias de control son el mecanismo central que permite a un programa modificar su flujo normal de ejecución secuencial (línea por línea).

| Categoría | Propósito Principal | Ejemplos en Kotlin |
| :--- | :--- | :--- |
| **Decisión** | Ejecutar un bloque de código u otro basándose en una condición. | `if`, `when` |
| **Repetición** | Ejecutar un bloque de código múltiples veces. | `for`, `while`, `do-while` |
| **Manejo de Errores** | Controlar y responder a situaciones inesperadas. | `try/catch/finally` |

---

## 🛠️ Detalle de Sintaxis y Uso Básico

### 1. IF / ELSE (Toma de Decisiones)

En Kotlin, `if` es una expresión que puede devolver un valor.

```kotlin
// IF/ELSE como sentencia
if (edad >= 18) {
    println("Mayor de edad")
} else if (edad > 0) {
    println("Menor de edad")
} else {
    println("Edad inválida")
}

### 2. WHEN (Alternativa a Switch/Múltiples Casos)
Permite evaluar una expresión contra múltiples ramas. Soporta rangos y tipos, siendo más potente que el switch de Java.
when(opcion) {
    1 -> println("Inicio")
    2 -> println("Configuración")
    in 3..5 -> println("Menú Secundario") // Uso de Rangos
    else -> println("Salir")
}

val listaNombres = listOf("Ana", "Beto", "Carlos")
for (nombre in listaNombres) {
    println("Hola ${nombre}")
}
