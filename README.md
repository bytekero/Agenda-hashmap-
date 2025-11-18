# 📒 Agenda de Contactos (Java)

Una aplicación de consola diseñada para gestionar contactos de forma eficiente. El proyecto implementa una estructura de datos optimizada para búsquedas rápidas y cuenta con un sistema de validación estricta de datos de entrada.

## 🛠️ Stack Tecnológico
* **Lenguaje:** Java (JDK 23).
* **Estructura de Datos:** `HashMap` (para acceso O(1)).
* **Validación:** Expresiones Regulares (Regex).
* **Entorno:** Proyecto estructura NetBeans.

## ✨ Características Técnicas

### 1. Estructura de Datos Optimizada
A diferencia de una lista convencional, este proyecto utiliza un **`HashMap<String, Persona>`** en la clase `Agenda`:
* **Clave (Key):** Se utiliza el **DNI** como identificador único.
* **Valor (Value):** Objeto `Persona`.
* **Beneficio:** Permite operaciones de búsqueda, inserción y eliminación instantáneas sin necesidad de recorrer toda la colección.

### 2. Validación de Datos (Regex)
La integridad de los datos se asegura en el constructor de la clase `Persona`. Si el formato no es correcto, el sistema rechaza la creación del contacto lanzando excepciones:
* **DNI:** Valida que sean 8 dígitos seguidos de una letra mayúscula (`\d{8}[A-Z]`).
* **Teléfono:** Valida que sean exactamente 9 dígitos numéricos (`\d{9}`).

### 3. Ejecución Concurrente
La clase principal `Miapp` extiende de **`Thread`**. La aplicación se lanza invocando el método `start()`, lo que ejecuta la lógica del menú dentro de su propio hilo de ejecución (`run()`), demostrando conocimientos en el manejo básico de hilos en Java.

## 📂 Arquitectura del Proyecto

El código fuente se encuentra en el paquete `DATA`:

| Archivo | Descripción |
| :--- | :--- |
| **`Persona.java`** | Define el objeto de datos. Incluye encapsulamiento y validación lógica con expresiones regulares. |
| **`Agenda.java`** | Gestiona la colección `HashMap`. Controla que no existan DNIs duplicados antes de agregar. |
| **`Miapp.java`** | Punto de entrada (`main`). Implementa la interfaz de usuario en consola (`Scanner`) y el bucle del menú. |

## 🚀 Instrucciones de Uso

1.  **Compilar:** Asegúrate de tener el JDK instalado.
2.  **Ejecutar:** Corre la clase `DATA.Miapp`.
3.  **Menú:**
    * Selecciona `1` para agregar (el sistema te pedirá Nombre, Teléfono y DNI).
    * Selecciona `2` para buscar un contacto instantáneamente por su DNI.
    * Selecciona `3` para borrar.
    * Selecciona `4` para ver el listado completo.

---
**Autor:** Antonio Muñoz
