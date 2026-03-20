## Generador de examenes con IA

Proyecto realizado por Gael López Bautista y Erick Iván Valeriano Santiago del grupo 602-A
de la carrera Ingeniería en computación

## Rutas del Frontend

Estas son las direcciones URL a las que los usuarios accederán a través de su navegador.

* **`/` (Inicio)**: Landing page del proyecto.
* **`/login`**: Página de autenticación para usuarios registrados.
* **`/registrarse`**: Formulario para la creación de cuentas de nuevos usuarios.
* **`/dashboard`**: Panel principal del usuario autenticado donde puede ver su información y puntaje acumulado.
* **`/juego`**: Interfaz principal donde se muestran las preguntas generadas y el usuario interactúa para responderlas.
* **`/admin`**: Panel de administración para gestionar la base de datos de preguntas de forma visual.

## Rutas del Backend

La API manejará el flujo de datos en formato JSON para las distintas entidades del sistema.

### Autenticación
* **`POST /api/auth/registro`**: Recibe los datos del frontend y registra un nuevo usuario en la base de datos.
* **`POST /api/auth/login`**: Valida las credenciales del usuario y genera la sesión.

### Gestión de Usuarios y Puntaje
* **`GET /api/usuarios`**: Devuelve la lista de usuarios.
* **`GET /api/usuarios/:id`**: Obtiene la información detallada de un usuario en específico.
* **`PUT /api/usuarios/:id`**: Actualiza los datos de perfil de un usuario.
* **`DELETE /api/usuarios/:id`**: Elimina una cuenta de usuario.
* **`PATCH /api/usuarios/:id/puntaje`**: Actualiza de forma específica el puntaje de un usuario tras finalizar una sesión de examen.

### Gestión del Banco de Preguntas
* **`GET /api/preguntas`**: Devuelve las preguntas almacenadas en la base de datos.
* **`POST /api/preguntas`**: Permite la inserción manual de una nueva pregunta.
* **`PUT /api/preguntas/:id`**: Actualiza el texto o las respuestas de una pregunta existente.
* **`DELETE /api/preguntas/:id`**: Elimina una pregunta del banco.

### Integración con Google Gemini
* **`POST /api/preguntas/generar`**: Este endpoint se comunica directamente con la API de Google. Al ejecutarse, solicita la generación de una nueva pregunta sobre programación web, la formatea correctamente y la inserta en la base de datos para expandir el banco de preguntas disponible.