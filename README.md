# Mis Recursos App

## Descripción

**Mis Recursos App** es una aplicación web que permite a los usuarios llevar un registro de su progreso al ver series, películas y leer libros. Los usuarios pueden añadir, modificar y eliminar registros de sus recursos, así como filtrarlos y buscarlos según diversos criterios.

## Link de descripcion del proyecto

- https://quilt-scarf-e7e.notion.site/Mis-recursos-app-207225c62602809eb49ceacd0ce10370

## Funcionalidades

### CRUD (Crear, Leer, Actualizar, Eliminar)

- **Crear**: Añadir un nuevo recurso con los siguientes campos:
  - Nombre del recurso
  - Género
  - Plataforma (Ej. Netflix, Amazon, HBO, Kindle, etc.)
  - Estado (En progreso, Terminado, Pendiente)
  - Formato (Serie, Película, Libro)
  - Fecha de terminación
  - Valoración final (1 a 5 estrellas)
  - Reseña personal

- **Leer**: Mostrar una lista de todos los recursos almacenados con la información relevante.

- **Actualizar**: Modificar los detalles de un recurso existente.

- **Eliminar**: Eliminar un recurso.

### Filtros y Búsqueda

- Filtrar recursos por:
  - Estado (Ej. Terminado, En progreso, Pendiente)
  - Formato (Ej. Serie, Película, Libro)
  - Plataforma (Ej. Netflix, Amazon, etc.)

- Barra de búsqueda para encontrar un recurso por su nombre.

## Diseño de la Base de Datos en MongoDB

### Colecciones

1. **usuarios**
   - `_id`: ObjectId
   - `nombre`: String
   - `email`: String
   - `fecha_creacion`: Date

2. **recursos**
   - `_id`: ObjectId
   - `usuario_id`: ObjectId (referencia a `usuarios`)
   - `nombre`: String
   - `genero`: String
   - `plataforma`: String
   - `estado`: String (En progreso, Terminado, Pendiente)
   - `formato`: String (Serie, Película, Libro)
   - `fecha_terminacion`: Date
   - `valoracion`: Number (1 a 5)
   - `reseña`: String
   - `fecha_creacion`: Date

### Índices

- Índice en `usuario_id` para mejorar la búsqueda de recursos por usuario.
- Índice compuesto en `estado`, `formato` y `plataforma` para optimizar los filtros.

## Comandos para Crear la Base de Datos y Colecciones

```bash

## Comando para Crear la Base de Datos:
use mis_recursos_app

## Comando para las colecciones: usuarios y recursos
db.createCollection("usuarios")
db.createCollection("recursos")

## Comando insercion de datos de "Usuario"

db.usuarios.insertOne({id:001, nombre: 'Brian Fair', apellido: 'Suarez Porras', email: 'briansuarez@hotmail.com', fecha_creacion: new Date() })

## Comando insercion de datos de  varios "Usuarios" con "insertMany"

db.usuarios.insertMany([
  {
    nombre: 'Brian',
    apellido: 'Fair',
    email: 'brian.fair@hotmail.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Lucía',
    apellido: 'Martínez',
    email: 'lucia.martinez@gmail.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Carlos',
    apellido: 'González',
    email: 'carlosg87@yahoo.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Sofía',
    apellido: 'Rojas',
    email: 'sofia.rojas@outlook.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Andrés',
    apellido: 'Ramírez',
    email: 'andresr@gmail.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Valentina',
    apellido: 'Mendoza',
    email: 'valen.mendoza@gmail.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Diego',
    apellido: 'Castillo',
    email: 'dcastillo@hotmail.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Camila',
    apellido: 'Silva',
    email: 'camila.silva@icloud.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Mateo',
    apellido: 'Herrera',
    email: 'mateo.herrera@yahoo.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Isabella',
    apellido: 'García',
    email: 'isagarcia@gmail.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Tomás',
    apellido: 'López',
    email: 'tomas.lopez@protonmail.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Florencia',
    apellido: 'Vega',
    email: 'flor.vega@gmail.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Julián',
    apellido: 'Navarro',
    email: 'julian.navarro@hotmail.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Antonella',
    apellido: 'Torres',
    email: 'anto.torres@gmail.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Sebastián',
    apellido: 'Pérez',
    email: 'sebaperez@yahoo.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Martina',
    apellido: 'Cruz',
    email: 'martina.cruz@gmail.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Agustín',
    apellido: 'Morales',
    email: 'agustinmorales@outlook.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Emilia',
    apellido: 'Ortega',
    email: 'emiliao@gmail.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Facundo',
    apellido: 'Reyes',
    email: 'facu.reyes@hotmail.com',
    fecha_creacion: new Date()
  },
  {
    nombre: 'Renata',
    apellido: 'Campos',
    email: 'renata.campos@gmail.com',
    fecha_creacion: new Date()
  }
]);

## Comando insercion de datos de "Recurso"

db.recursos.insertOne({id:001, usuario_id: 001, nombre: 'Dark', genero: 'suspenso', plataforma: 'Netflix', estado: 'En progreso', formato: 'Serie', fecha_creacion: new Date()})

## Comando insercion de datos de varios "Recursos" con "insertMany"

db.recursos.insertMany([
  { usuario_id: 1, nombre: 'Dark', genero: 'Suspenso', plataforma: 'Netflix', estado: 'En progreso', formato: 'Serie', fecha_creacion: new Date() },
  { usuario_id: 2, nombre: 'The Office', genero: 'Comedia', plataforma: 'Amazon', estado: 'Terminado', formato: 'Serie', fecha_creacion: new Date() },
  { usuario_id: 3, nombre: '1984', genero: 'Distopía', plataforma: 'Kindle', estado: 'Pendiente', formato: 'Libro', fecha_creacion: new Date() },
  { usuario_id: 4, nombre: 'Inception', genero: 'Ciencia ficción', plataforma: 'HBO', estado: 'Terminado', formato: 'Película', fecha_creacion: new Date() },
  { usuario_id: 5, nombre: 'Stranger Things', genero: 'Ciencia ficción', plataforma: 'Netflix', estado: 'En progreso', formato: 'Serie', fecha_creacion: new Date() },
  { usuario_id: 6, nombre: 'El psicoanalista', genero: 'Thriller', plataforma: 'Kindle', estado: 'Terminado', formato: 'Libro', fecha_creacion: new Date() },
  { usuario_id: 7, nombre: 'Breaking Bad', genero: 'Drama', plataforma: 'Netflix', estado: 'Terminado', formato: 'Serie', fecha_creacion: new Date() },
  { usuario_id: 8, nombre: 'Interstellar', genero: 'Ciencia ficción', plataforma: 'Amazon', estado: 'Pendiente', formato: 'Película', fecha_creacion: new Date() },
  { usuario_id: 9, nombre: 'Dune', genero: 'Fantasía', plataforma: 'Kindle', estado: 'En progreso', formato: 'Libro', fecha_creacion: new Date() },
  { usuario_id: 10, nombre: 'Friends', genero: 'Comedia', plataforma: 'HBO', estado: 'Terminado', formato: 'Serie', fecha_creacion: new Date() },
  { usuario_id: 11, nombre: 'Matrix', genero: 'Acción', plataforma: 'Amazon', estado: 'Pendiente', formato: 'Película', fecha_creacion: new Date() },
  { usuario_id: 12, nombre: 'Mindhunter', genero: 'Crimen', plataforma: 'Netflix', estado: 'En progreso', formato: 'Serie', fecha_creacion: new Date() },
  { usuario_id: 13, nombre: 'El alquimista', genero: 'Ficción', plataforma: 'Kindle', estado: 'Pendiente', formato: 'Libro', fecha_creacion: new Date() },
  { usuario_id: 14, nombre: 'Better Call Saul', genero: 'Drama', plataforma: 'Netflix', estado: 'Terminado', formato: 'Serie', fecha_creacion: new Date() },
  { usuario_id: 15, nombre: 'La La Land', genero: 'Romance', plataforma: 'Amazon', estado: 'Terminado', formato: 'Película', fecha_creacion: new Date() },
  { usuario_id: 16, nombre: 'The Witcher', genero: 'Fantasía', plataforma: 'Netflix', estado: 'En progreso', formato: 'Serie', fecha_creacion: new Date() },
  { usuario_id: 17, nombre: 'Sapiens', genero: 'Historia', plataforma: 'Kindle', estado: 'En progreso', formato: 'Libro', fecha_creacion: new Date() },
  { usuario_id: 18, nombre: 'Tenet', genero: 'Acción', plataforma: 'HBO', estado: 'Terminado', formato: 'Película', fecha_creacion: new Date() },
  { usuario_id: 19, nombre: 'House of Cards', genero: 'Drama', plataforma: 'Netflix', estado: 'Terminado', formato: 'Serie', fecha_creacion: new Date() },
  { usuario_id: 20, nombre: 'El Hobbit', genero: 'Fantasía', plataforma: 'Kindle', estado: 'Pendiente', formato: 'Libro', fecha_creacion: new Date() },
  { usuario_id: 1, nombre: 'Black Mirror', genero: 'Ficción', plataforma: 'Netflix', estado: 'En progreso', formato: 'Serie', fecha_creacion: new Date() },
  { usuario_id: 2, nombre: 'El código Da Vinci', genero: 'Misterio', plataforma: 'Kindle', estado: 'Pendiente', formato: 'Libro', fecha_creacion: new Date() },
  { usuario_id: 3, nombre: 'Avatar', genero: 'Fantasía', plataforma: 'Amazon', estado: 'Terminado', formato: 'Película', fecha_creacion: new Date() },
  { usuario_id: 4, nombre: 'Narcos', genero: 'Crimen', plataforma: 'Netflix', estado: 'En progreso', formato: 'Serie', fecha_creacion: new Date() },
  { usuario_id: 5, nombre: 'Steve Jobs', genero: 'Biografía', plataforma: 'Kindle', estado: 'Terminado', formato: 'Libro', fecha_creacion: new Date() },
  { usuario_id: 6, nombre: 'The Crown', genero: 'Histórico', plataforma: 'Netflix', estado: 'En progreso', formato: 'Serie', fecha_creacion: new Date() },
  { usuario_id: 7, nombre: 'Bohemian Rhapsody', genero: 'Biografía', plataforma: 'HBO', estado: 'Pendiente', formato: 'Película', fecha_creacion: new Date() },
  { usuario_id: 8, nombre: 'Cómo ganar amigos', genero: 'Autoayuda', plataforma: 'Kindle', estado: 'Terminado', formato: 'Libro', fecha_creacion: new Date() },
  { usuario_id: 9, nombre: 'The Boys', genero: 'Acción', plataforma: 'Amazon', estado: 'En progreso', formato: 'Serie', fecha_creacion: new Date() },
  { usuario_id: 10, nombre: 'Don Quijote', genero: 'Clásico', plataforma: 'Kindle', estado: 'Pendiente', formato: 'Libro', fecha_creacion: new Date() },
  { usuario_id: 11, nombre: 'The Mandalorian', genero: 'Ciencia ficción', plataforma: 'Disney+', estado: 'En progreso', formato: 'Serie', fecha_creacion: new Date() },
  { usuario_id: 12, nombre: 'Shutter Island', genero: 'Thriller', plataforma: 'Amazon', estado: 'Terminado', formato: 'Película', fecha_creacion: new Date() },
  { usuario_id: 13, nombre: 'Rebelión en la granja', genero: 'Fábula política', plataforma: 'Kindle', estado: 'Terminado', formato: 'Libro', fecha_creacion: new Date() },
  { usuario_id: 14, nombre: 'Black Swan', genero: 'Psicológico', plataforma: 'HBO', estado: 'Pendiente', formato: 'Película', fecha_creacion: new Date() },
  { usuario_id: 15, nombre: 'Vikings', genero: 'Histórico', plataforma: 'Netflix', estado: 'En progreso', formato: 'Serie', fecha_creacion: new Date() },
  { usuario_id: 16, nombre: 'Educated', genero: 'Memorias', plataforma: 'Kindle', estado: 'Terminado', formato: 'Libro', fecha_creacion: new Date() },
  { usuario_id: 17, nombre: 'Peaky Blinders', genero: 'Crimen', plataforma: 'Netflix', estado: 'Terminado', formato: 'Serie', fecha_creacion: new Date() },
  { usuario_id: 18, nombre: 'Fight Club', genero: 'Drama', plataforma: 'Amazon', estado: 'Terminado', formato: 'Película', fecha_creacion: new Date() },
  { usuario_id: 19, nombre: 'El poder del ahora', genero: 'Espiritualidad', plataforma: 'Kindle', estado: 'En progreso', formato: 'Libro', fecha_creacion: new Date() },
  { usuario_id: 20, nombre: 'Chernobyl', genero: 'Drama', plataforma: 'HBO', estado: 'Terminado', formato: 'Serie', fecha_creacion: new Date() }
]);

## Filtros y Búsqueda:

# 1) Leer: Mostrar una lista de todos los recursos almacenados con la información relevante.

# 2) Actualizar: Permitir al usuario modificar los detalles de un recurso existente.

# 3) Eliminar: Permitir al usuario eliminar un recurso.

# 4) Estado (Ej. Terminado, En progreso, Pendiente).

# 5) Formato (Ej. Serie, Película, Libro).

# 6) Plataforma (Ej. Netflix, Amazon, etc.).

