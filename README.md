# 📌 Entrega Final – Backend 3

## 🔹 Descripción
Proyecto **AdoptMe API – Backend III**.  
Incluye CRUD de usuarios y mascotas, adopciones, autenticación con JWT, documentación con Swagger y despliegue con Docker Compose.

---

## 🔹 Instalación local

```bash
# Clonar el repositorio
git clone <URL_REPO>
cd backend3-entrega1

# Instalar dependencias
npm install


Variables de entorno
Este proyecto requiere un archivo .env en la raíz con las siguientes variables:
- PORT: Puerto en el que corre la API (ej: 8080).
- MONGO_URL: Cadena de conexión a MongoDB Atlas.
- JWT_SECRET: Secreto para firmar tokens JWT.
⚠️ El archivo .env no está en el repositorio por seguridad.
Se entrega al profesor por separado para la evaluación.
En el repo se incluye un .env.example como referencia.
Levantar servidor en desarrollo
npm run dev



🔹 Endpoints principales
👤 Users
- GET /api/users → listar usuarios
- GET /api/users/{uid} → obtener usuario por ID
- PUT /api/users/{uid} → actualizar usuario
- DELETE /api/users/{uid} → eliminar usuario
🐶 Pets
- GET /api/pets → listar mascotas
- POST /api/pets → crear mascota
- PUT /api/pets/{pid} → actualizar mascota
- DELETE /api/pets/{pid} → eliminar mascota
❤️ Adoptions
- GET /api/adoptions → listar adopciones
- POST /api/adoptions/{uid}/{pid} → crear adopción
🔑 Sessions
- POST /api/sessions/register → registrar usuario
- POST /api/sessions/login → iniciar sesión (JWT)
- GET /api/sessions/current → obtener usuario actual (cookie protegida)

🔹 Documentación Swagger
Disponible en:
http://localhost:8080/api/docs

🔹 Docker Compose
Este proyecto se ejecuta con Docker Compose en lugar de docker run.
La elección de Compose garantiza:
- Lectura automática de las variables de entorno desde .env.
- Mapeo consistente del puerto 8080:8080.
- Contenedor con nombre fijo (adoptme-api).
- Reproducibilidad: el evaluador puede levantar el proyecto con un solo comando.
Comandos principales
# Construir y levantar servicios
docker compose up --build

# Detener servicios
docker compose down


Una vez levantado, la API estará disponible en:
- Swagger: http://localhost:8080/api/docs
- Endpoint de mascotas: http://localhost:8080/api/pets

🔹 Validaciones
- Usuarios: email único, contraseña encriptada.
- Mascotas: specie obligatoria.
- Adopciones: relación entre usuario y mascota.
- JWT: protege endpoints sensibles.
- Middleware de errores: respuestas claras (400, 404, 500).

🔹 Evidencia de pruebas
- Colección Postman exportada.
- Capturas de Swagger mostrando endpoints funcionando.
- Ejemplo de adopción exitosa en Atlas.
