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
  {
    usuario_id: 11,
    nombre: "Friends",
    genero: "Romance",
    plataforma: "Netflix",
    estado: "Terminado",
    formato: "Película",
    fecha_creacion: ISODate("2025-01-27T16:45:57.799645"),
    fecha_terminacion: ISODate("2025-02-06T16:45:57.799645"),
    valoracion: 1,
    reseña: "Excelente desarrollo de personajes."
  },
  {
    usuario_id: 20,
    nombre: "Rebelión en la granja",
    genero: "Drama",
    plataforma: "Netflix",
    estado: "Terminado",
    formato: "Serie",
    fecha_creacion: ISODate("2025-05-01T16:45:57.799672"),
    fecha_terminacion: ISODate("2025-05-31T16:45:57.799672"),
    valoracion: 2,
    reseña: "Demasiado predecible."
  },
  {
    usuario_id: 10,
    nombre: "Fight Club",
    genero: "Thriller",
    plataforma: "HBO",
    estado: "En progreso",
    formato: "Libro",
    fecha_creacion: ISODate("2025-06-03T16:45:57.799690")
  },
  {
    usuario_id: 10,
    nombre: "Cómo ganar amigos",
    genero: "Drama",
    plataforma: "Amazon",
    estado: "En progreso",
    formato: "Serie",
    fecha_creacion: ISODate("2025-02-17T16:45:57.799700")
  },
  {
    usuario_id: 2,
    nombre: "The Mandalorian",
    genero: "Fantasía",
    plataforma: "Kindle",
    estado: "Pendiente",
    formato: "Libro",
    fecha_creacion: ISODate("2024-12-07T16:45:57.799711")
  },
  {
    usuario_id: 20,
    nombre: "Shutter Island",
    genero: "Thriller",
    plataforma: "Kindle",
    estado: "Terminado",
    formato: "Película",
    fecha_creacion: ISODate("2025-02-19T16:45:57.799725"),
    fecha_terminacion: ISODate("2025-02-24T16:45:57.799725"),
    valoracion: 2,
    reseña: "La volvería a ver sin duda."
  },
  {
    usuario_id: 5,
    nombre: "Rebelión en la granja",
    genero: "Autoayuda",
    plataforma: "Amazon",
    estado: "En progreso",
    formato: "Serie",
    fecha_creacion: ISODate("2025-01-17T16:45:57.799735")
  },
  {
    usuario_id: 2,
    nombre: "Dark",
    genero: "Autoayuda",
    plataforma: "Kindle",
    estado: "Pendiente",
    formato: "Película",
    fecha_creacion: ISODate("2025-02-16T16:45:57.799747")
  },
  {
    usuario_id: 14,
    nombre: "Steve Jobs",
    genero: "Ciencia ficción",
    plataforma: "Amazon",
    estado: "Terminado",
    formato: "Serie",
    fecha_creacion: ISODate("2025-01-30T16:45:57.799758"),
    fecha_terminacion: ISODate("2025-02-24T16:45:57.799758"),
    valoracion: 4,
    reseña: "Demasiado predecible."
  },
  {
    usuario_id: 14,
    nombre: "Dark",
    genero: "Comedia",
    plataforma: "HBO",
    estado: "Terminado",
    formato: "Libro",
    fecha_creacion: ISODate("2025-04-11T16:45:57.799773"),
    fecha_terminacion: ISODate("2025-04-22T16:45:57.799773"),
    valoracion: 4,
    reseña: "Buena historia, aunque un poco lenta."
  },
  {
    usuario_id: 5,
    nombre: "El psicoanalista",
    genero: "Suspenso",
    plataforma: "HBO",
    estado: "Terminado",
    formato: "Libro",
    fecha_creacion: ISODate("2025-04-15T16:45:57.799786"),
    fecha_terminacion: ISODate("2025-04-16T16:45:57.799786"),
    valoracion: 3,
    reseña: "Impresionante desde lo visual hasta la trama."
  },
  {
    usuario_id: 7,
    nombre: "El Hobbit",
    genero: "Acción",
    plataforma: "HBO",
    estado: "En progreso",
    formato: "Libro",
    fecha_creacion: ISODate("2024-12-11T16:45:57.799794")
  },
  {
    usuario_id: 6,
    nombre: "Rebelión en la granja",
    genero: "Drama",
    plataforma: "Disney+",
    estado: "Terminado",
    formato: "Serie",
    fecha_creacion: ISODate("2025-03-11T16:45:57.799798"),
    fecha_terminacion: ISODate("2025-03-26T16:45:57.799798"),
    valoracion: 5,
    reseña: "Excelente desarrollo de personajes."
  },
  {
    usuario_id: 12,
    nombre: "The Office",
    genero: "Ciencia ficción",
    plataforma: "Disney+",
    estado: "Pendiente",
    formato: "Serie",
    fecha_creacion: ISODate("2025-01-22T16:45:57.799805")
  },
  {
    usuario_id: 9,
    nombre: "The Witcher",
    genero: "Drama",
    plataforma: "HBO",
    estado: "Pendiente",
    formato: "Película",
    fecha_creacion: ISODate("2025-02-28T16:45:57.799810")
  },
  {
    usuario_id: 14,
    nombre: "The Crown",
    genero: "Suspenso",
    plataforma: "Netflix",
    estado: "Pendiente",
    formato: "Serie",
    fecha_creacion: ISODate("2025-01-19T16:45:57.799815")
  },
  {
    usuario_id: 20,
    nombre: "The Boys",
    genero: "Romance",
    plataforma: "Kindle",
    estado: "En progreso",
    formato: "Serie",
    fecha_creacion: ISODate("2025-05-24T16:45:57.799819")
  },
  {
    usuario_id: 4,
    nombre: "House of Cards",
    genero: "Ciencia ficción",
    plataforma: "Amazon",
    estado: "Terminado",
    formato: "Libro",
    fecha_creacion: ISODate("2025-01-28T16:45:57.799824"),
    fecha_terminacion: ISODate("2025-02-27T16:45:57.799824"),
    valoracion: 3,
    reseña: "Excelente desarrollo de personajes."
  },
  {
    usuario_id: 15,
    nombre: "Vikings",
    genero: "Romance",
    plataforma: "Netflix",
    estado: "En progreso",
    formato: "Película",
    fecha_creacion: ISODate("2025-03-03T16:45:57.799831")
  },
  {
    usuario_id: 12,
    nombre: "Dark",
    genero: "Autoayuda",
    plataforma: "Amazon",
    estado: "Terminado",
    formato: "Película",
    fecha_creacion: ISODate("2025-02-21T16:45:57.799836"),
    fecha_terminacion: ISODate("2025-02-24T16:45:57.799836"),
    valoracion: 2,
    reseña: "Entretenida y bien lograda."
  },
  {
    usuario_id: 20,
    nombre: "The Crown",
    genero: "Autoayuda",
    plataforma: "Netflix",
    estado: "Terminado",
    formato: "Película",
    fecha_creacion: ISODate("2025-05-06T16:45:57.799843"),
    fecha_terminacion: ISODate("2025-05-21T16:45:57.799843"),
    valoracion: 3,
    reseña: "No cumplió mis expectativas."
  },
  {
    usuario_id: 15,
    nombre: "Breaking Bad",
    genero: "Comedia",
    plataforma: "Disney+",
    estado: "Pendiente",
    formato: "Libro",
    fecha_creacion: ISODate("2025-02-17T16:45:57.799850")
  },
  {
    usuario_id: 2,
    nombre: "Shutter Island",
    genero: "Drama",
    plataforma: "HBO",
    estado: "En progreso",
    formato: "Libro",
    fecha_creacion: ISODate("2025-02-05T16:45:57.799855")
  },
  {
    usuario_id: 3,
    nombre: "Dune",
    genero: "Thriller",
    plataforma: "Netflix",
    estado: "Terminado",
    formato: "Serie",
    fecha_creacion: ISODate("2025-04-03T16:45:57.799860"),
    fecha_terminacion: ISODate("2025-04-20T16:45:57.799860"),
    valoracion: 5,
    reseña: "Obra maestra, de principio a fin."
  },
  {
    usuario_id: 5,
    nombre: "El Alquimista",
    genero: "Autoayuda",
    plataforma: "Kindle",
    estado: "Pendiente",
    formato: "Libro",
    fecha_creacion: ISODate("2025-06-01T16:45:57.799865")
  },
  {
    usuario_id: 9,
    nombre: "The Witcher",
    genero: "Fantasía",
    plataforma: "Netflix",
    estado: "En progreso",
    formato: "Serie",
    fecha_creacion: ISODate("2025-03-25T16:45:57.799870")
  },
  {
    usuario_id: 17,
    nombre: "Mindhunter",
    genero: "Thriller",
    plataforma: "Amazon",
    estado: "Terminado",
    formato: "Serie",
    fecha_creacion: ISODate("2025-01-10T16:45:57.799875"),
    fecha_terminacion: ISODate("2025-02-09T16:45:57.799875"),
    valoracion: 4,
    reseña: "Enganchante, con giros interesantes."
  },
  {
    usuario_id: 6,
    nombre: "The Social Dilemma",
    genero: "Documental",
    plataforma: "Netflix",
    estado: "Terminado",
    formato: "Película",
    fecha_creacion: ISODate("2024-12-29T16:45:57.799880"),
    fecha_terminacion: ISODate("2025-01-03T16:45:57.799880"),
    valoracion: 3,
    reseña: "Hace reflexionar, pero algo repetitivo."
  },
  {
    usuario_id: 19,
    nombre: "Peaky Blinders",
    genero: "Acción",
    plataforma: "HBO",
    estado: "En progreso",
    formato: "Serie",
    fecha_creacion: ISODate("2025-03-01T16:45:57.799885")
  },
  {
    usuario_id: 8,
    nombre: "Narcos",
    genero: "Crimen",
    plataforma: "Amazon",
    estado: "Pendiente",
    formato: "Serie",
    fecha_creacion: ISODate("2025-01-07T16:45:57.799890")
  },
  {
    usuario_id: 4,
    nombre: "BoJack Horseman",
    genero: "Comedia",
    plataforma: "Netflix",
    estado: "Terminado",
    formato: "Serie",
    fecha_creacion: ISODate("2025-03-12T16:45:57.799895"),
    fecha_terminacion: ISODate("2025-04-01T16:45:57.799895"),
    valoracion: 5,
    reseña: "Una mezcla genial de humor y profundidad."
  }
]);

## Filtros y Búsqueda:

# 1) Leer: Mostrar una lista de todos los recursos almacenados con la información relevante.

db.recursos.find()

# Muestra todos los documentos de la coleccion "recursos"

# 2) Actualizar: Permitir al usuario modificar los detalles de un recurso existente.

db.usuarios.insertOne({id:001, nombre: 'Brian Fair', apellido: 'Suarez Porras', email: 'briansuarez@hotmail.com', fecha_creacion: new Date(), favoritos: ["Friends", "Fight Club"]}) 

# Se agrego un usuario con una lista de favoritos para poder hacer el ejemplo de este punto

db.usuarios.updateOne({nombre: "Brian Fair"}, {$push: {favoritos: "Dark"}})

# Agrega al usuario "Brian Fair" en la lista de Favoritos la serie "Dark"

# 3) Eliminar: Permitir al usuario eliminar un recurso.

db.usuarios.deleteOne({usuario_id: 15})

# Eliminamos el usuario con id: 15 de la coleccion de usuarios

# 4) Estado (Ej. Terminado, En progreso, Pendiente).

db.recursos.find({estado: "Terminado"})

# Mostramos todos los documentos de la coleccion recursos cuyo estado sea "Terminado"

# 5) Formato (Ej. Serie, Película, Libro).

db.recursos.find({formato: "Película"})

# Mostramos todos los documentos de la coleccion recursos cuyo formato sea "Pelicula"

# 6) Plataforma (Ej. Netflix, Amazon, etc.).

db.recursos.find({plataforma: "Netflix"})

# Mostramos todos los documentos de la coleccion recursos a plataforma sea "Netflix"