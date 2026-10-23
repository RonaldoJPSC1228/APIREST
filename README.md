# API REST de usuarios (Node.js + Express + MySQL)

API REST para gestionar usuarios (CRUD completo) sobre una base de datos MySQL. La base de datos está alojada en **Railway** y el servicio se despliega en **Render**.

## Tecnologías

Node.js, Express, mysql2, dotenv

## Endpoints

| Método | Ruta | Descripción |
|---|---|---|
| GET | `/prueba` | Verifica la conexión con la base de datos |
| GET | `/api/usuarios` | Lista todos los usuarios |
| GET | `/api/usuarios/:id` | Obtiene un usuario por id |
| POST | `/api/usuarios` | Crea un usuario (`nombre`, `apellido`, `direccion`) |
| PATCH | `/api/usuarios/:id` | Actualiza los campos enviados de un usuario |
| DELETE | `/api/usuarios/:id` | Elimina un usuario |

Las rutas que no existen responden 404 con un mensaje en JSON.

## Base de datos

```sql
CREATE TABLE usuarios (
  id INT(10) NOT NULL AUTO_INCREMENT,
  nombre VARCHAR(30) DEFAULT NULL,
  apellido VARCHAR(30) DEFAULT NULL,
  direccion VARCHAR(30) DEFAULT NULL,
  PRIMARY KEY (id)
);
```

## Variables de entorno

Crea un archivo `.env` en la raíz:

```
PORT=5000
DB_HOST=
DB_PORT=3306
DB_USER=
DB_PASSWORD=
DB_DATABASE=
```

## Ejecución local

```bash
npm install
npm run dev
```

## Despliegue

1. Crea una base de datos MySQL en Railway y ejecuta el script de la tabla.
2. En Render, crea un *Web Service* conectado a este repositorio.
3. Usa `npm install` como comando de build y `npm start` como comando de inicio.
4. Configura las variables de entorno con los datos de conexión de Railway.
