# Mi stack en docker compose - Lab 1

Este proyecto levanta una aplicación Node.js junto a una base de datos MySQL utilizando docker-compose.  

## Estructura del .env
Es necesario crear un archivo .env en la raíz del proyecto, definiendo las siguientes variables:


```bash
DB_USERNAME=myuser
DB_PASSWORD=mypass
DB_NAME=mydb
DB_HOST=localhost
DB_PORT=3306
DB_TYPE=mysql
MYSQL_ROOT_PASSWORD=rootpass
PORT=8080
```

## Levantar el proyecto
Para construir y ejecutar los servicios:

```bash
docker compose up -d
```

## Puertos

- La aplicación en el puerto 8080
- La base de datos MySQL en el puerto 3306

## Creación de tabla inicial en MySQL

La tabla usuarios se crea automáticamente al iniciar MySQL por primera vez, según el script init.sql.

## Ejemplos

### Crear usuario
```bash
curl -X POST http://localhost:8080/users -H "Content-Type: application/json" -d '{"nombre":"Carlos López","edad":28}'
```

### Listar usuarios
```bash
curl http://localhost:8080/users
```

