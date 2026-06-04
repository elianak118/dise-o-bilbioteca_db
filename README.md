
# 📚 Sistema de Gestión de Biblioteca Universitaria (Diseño de Base de Datos)

Este proyecto consiste en  **diseñar y crear una estructura relacional desde cero** utilizando SQL y phpMyAdmin (XAMPP).

El objetivo es resolver un problema común: organizar los libros, autores y préstamos de una biblioteca universitaria de forma eficiente y sin errores de duplicidad.

---

## 📐 Modelo de Datos y Relaciones

El sistema se compone de 3 tablas principales conectadas entre sí mediante Llaves Primarias (`PRIMARY KEY`) y Llaves Foráneas (`FOREIGN KEY`):

1. **`autores`** (Tabla Maestra): Almacena la información de los escritores.
2. **`libros`**: Guarda los datos de los libros y se conecta con la tabla `autores` (Relación: Un autor puede escribir muchos libros).
3. **`prestamos`** *(Próximamente)*: Registrará qué alumno se lleva qué libro.

---

## 🛠️ Creación de Tablas (Paso a Paso)

### 1. Tabla: `autores`
Esta tabla fue diseñada para identificar de forma única a cada autor del sistema.

* **Estructura lógica:**
  * `id_autor`: Tipo `INT`, Llave Primaria y Autoincrementable. 
  * `nombre`: Tipo `VARCHAR(100)`. 
  * `nacionalidad`: Tipo `VARCHAR(50)`.

