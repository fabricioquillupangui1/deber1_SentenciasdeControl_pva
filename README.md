
---

# 📘 Sentencias de Control y Jetpack Compose en Kotlin

Este repositorio contiene ejemplos claros y prácticos sobre las **sentencias de control en Kotlin**, su uso avanzado y su aplicación real en **Jetpack Compose** para Android.
El objetivo es comprender cómo el **flujo de control** gobierna tanto la lógica del programa como la interacción de la interfaz de usuario.

---

## 🔹 1. WHEN (Alternativa a Switch / Múltiples Casos)

La sentencia `when` reemplaza al `switch` de Java. Permite evaluar una expresión contra múltiples condiciones y puede usarse como **sentencia** o como **expresión** (devuelve un valor).

### Características:

* Soporta valores directos
* Rangos (`in`)
* Condiciones múltiples
* Caso por defecto (`else`)

```kotlin
when (opcion) {
    1 -> println("Inicio")
    2 -> println("Configuración")
    in 3..5 -> println("Menú Secundario")
    else -> println("Salir")
}
```

---

## 🔹 2. BUCLE FOR (Iteración)

El bucle `for` se utiliza para iterar sobre cualquier estructura iterable como listas, arrays, rangos o colecciones.

```kotlin
val listaNombres = listOf("Ana", "Beto", "Carlos")
for (nombre in listaNombres) {
    println("Hola $nombre")
}
```

---

## 🔹 3. WHILE / DO WHILE (Bucles Condicionales)

* `while`: Ejecuta el bloque **mientras** la condición sea verdadera.
* `do-while`: Ejecuta el bloque **al menos una vez**, luego evalúa la condición.

```kotlin
var contador = 0
while (contador < 3) {
    println("Contando: $contador")
    contador++
}
```

---

## 🔹 4. TRY / CATCH / FINALLY (Manejo de Excepciones)

Permite manejar errores en tiempo de ejecución.

```kotlin
try {
    val x = 10 / 0
} catch (e: Exception) {
    println("Error: División por cero")
} finally {
    println("Operación finalizada")
}
```

---

## 🔹 5. BREAK / CONTINUE (Control de Bucles)

* `break`: Termina el bucle.
* `continue`: Salta la iteración actual.

```kotlin
for (i in 1..10) {
    if (i % 2 != 0) continue
    println(i)
    if (i == 6) break
}
```

---

## 🔹 6. Operador Elvis `?:` (Null Safety)

Proporciona un valor por defecto cuando una variable es `null`.

```kotlin
val usuario: String? = null
val nombre = usuario ?: "Invitado"
println(nombre)
```

---

## 🔹 7. Corrutinas (Control Asíncrono)

Las corrutinas permiten manejar tareas asíncronas sin bloquear el hilo principal.

```kotlin
GlobalScope.launch {
    delay(1000)
    println("Tarea completada en segundo plano")
}
```

---

# 🚀 Sentencias de Control Avanzadas en Kotlin

## 🔸 Operadores Lógicos y Relacionales

```kotlin
val edad = 20
if (edad >= 18 && edad <= 65) {
    println("Edad válida para trabajar")
}
```

---

## 🔸 Rangos de Valores

```kotlin
for (i in 10 downTo 1 step 2) {
    println(i)
}
```

---

## 🔸 Funciones de Colecciones

```kotlin
val numeros = listOf(1,2,3,4,5)
numeros.forEachIndexed { index, valor ->
    println("Índice $index = $valor")
}
```

---

## 🔸 Etiquetas (`break@label`)

```kotlin
loop@ for (i in 1..5) {
    for (j in 1..5) {
        if (j == 3) break@loop
        println("i=$i j=$j")
    }
}
```

---

## 🔸 TRY / CATCH como Expresión

```kotlin
val resultado = try {
    10 / 2
} catch (e: Exception) {
    0
}
```

---

## 🔸 Scope Functions (Flujo con Lambdas)

```kotlin
val persona = Persona().apply {
    nombre = "Fabricio"
    edad = 22
}
```

---

# 🛠️ Componentes Fundamentales de Jetpack Compose

## Componentes principales:

* **MainActivity.kt** → Punto de entrada y Composable raíz
* **TextUi** → Componente de texto reutilizable
* **TextFieldUi** → Entrada de datos
* **AlertDialogUi** → Diálogos modales

---

## 📁 TextUI.kt

```kotlin
@Composable
fun TextUi(text: String) {
    Text(
        text = text,
        color = Color.Green,
        fontSize = 20.sp,
        fontWeight = FontWeight.Bold,
        modifier = Modifier
            .fillMaxWidth()
            .background(Color.Blue),
        textAlign = TextAlign.Center
    )
}
```

---

## 📁 TextFieldUi.kt

```kotlin
@Composable
fun CreateTextField(
    valor: String,
    label: String,
    onValue: (String) -> Unit
) {
    TextField(
        value = valor,
        onValueChange = onValue,
        label = { Text(label) },
        modifier = Modifier
            .fillMaxWidth()
            .padding(10.dp)
    )
}
```

---

## 📁 AlertDialogUi.kt

```kotlin
@Composable
fun AlertDialogUi(
    titulo: String,
    mensaje: String,
    dissmissButton: () -> Unit,
    confirmButton: () -> Unit
) {
    AlertDialog(
        onDismissRequest = dissmissButton,
        title = { Text(titulo) },
        text = { Text(mensaje) },
        confirmButton = {
            TextButton(onClick = confirmButton) {
                Text("Continuar")
            }
        },
        dismissButton = {
            TextButton(onClick = dissmissButton) {
                Text("Regresar")
            }
        }
    )
}
```

---

# 🎯 Ejercicios Prácticos

## 🧮 Ejercicio 1: Clasificador Par / Impar

**Conceptos utilizados:**

* `if / else` como expresión
* Estados (`rememberSaveable`)
* Control de visibilidad con `if`
* AlertDialog

📌 Clasifica dos números ingresados por el usuario como **Par** o **Impar**.

---

## 🔐 Ejercicio 2: Login Simplificado

**Conceptos utilizados:**

* Variables de estado
* Lambdas
* AlertDialog controlado por estado

📌 Muestra un mensaje de ingreso exitoso al presionar el botón.

---

# ✅ Conclusión

Este repositorio demuestra cómo las **sentencias de control en Kotlin** no solo gobiernan la lógica del programa, sino que también controlan directamente el **flujo visual y la interacción** en Jetpack Compose, permitiendo crear aplicaciones claras, reactivas y mantenibles.

---

<h1>Ejercicios prácticos y Readme (Dar click en los enlaces)</h1>
<a href="https://drive.google.com/file/d/15FVqpBPP9jeUe7Jluji94yOcqyPRi9ci/view?usp=sharing">Video de los 2 ejercicios prácticos</a><br>
<a href="https://github.com/fabricioquillupangui1/deber1_SentenciasdeControl_pva/blob/main/README.md">Enlace de github a Readme</a>
