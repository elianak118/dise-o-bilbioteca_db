
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

## 🛠️ Creación de Tablas

### 1. Tabla: `autores`
Esta tabla fue diseñada para identificar de forma única a cada autor del sistema.

* **Estructura lógica:**
  * `id_autor`: Tipo `INT`, Llave Primaria y Autoincrementable. 
  * `nombre`: Tipo `VARCHAR(100)`. 
  * `nacionalidad`: Tipo `VARCHAR(50)`.

### 2. Tabla: `libros`
Esta tabla almacena los libros de la biblioteca y está conectada directamente con la tabla de `autores` mediante una relación de "uno a muchos" (un autor puede tener muchos libros escritos, pero un libro solo pertenece a un autor).

* **Estructura lógica creada manualmente:**
  * `id_libro`: Tipo `INT`, Llave Primaria y con `AUTO_INCREMENT` activo.
  * `titulo`: Tipo `VARCHAR(150)` para soportar títulos largos.
  * `anio_publicacion`: Tipo `INT` para almacenar el año en formato numérico.
  * `autor_id`: Tipo `INT`, definido como **(`FOREIGN KEY`)**.
 
### 3. Tabla: `prestamos`
Esta tabla funciona como el registro histórico de movimientos de la biblioteca. Su objetivo es mapear qué estudiante tiene qué libro y los plazos de entrega. Es una tabla transaccional que maneja relaciones complejas.

* **Estructura lógica creada de forma visual:**
  * `id_prestamo`: Tipo `INT`, Llave Primaria y Autoincrementable.
  * `nombre_alumno`: Tipo `VARCHAR(100)` para registrar al estudiante.
  * `libro_id`: Tipo `INT`, definido como **(`FOREIGN KEY`)** hacia la tabla `libros`.
  * `fecha_prestamo`: Tipo `DATE` (Registra el día de salida).
  * `fecha_devolucion`: Tipo `DATE` (Registra el día límite de entrega).
 
### 4. Inserción de Datos en la Tabla `autores`
Dado que la columna `id_autor` fue configurada con `AUTO_INCREMENT`, no es necesario especificar el ID manualmente; el motor de la base de datos genera los identificadores de forma secuencial y automática.


