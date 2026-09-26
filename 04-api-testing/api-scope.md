# API Testing — Alcance

## API
Swagger Petstore

## Alcance funcional
Gestión de mascotas (pet).

## Operaciones seleccionadas

| Método HTTP | Endpoint | Propósito |
|---|---|---|
| POST | /pet | Registrar una nueva mascota |
| GET | /pet/{petId} | Consultar una mascota por su identificador |
| PUT | /pet | Modificar los datos de una mascota existente |
| DELETE | /pet/{petId} | Eliminar una mascota existente |

## Justificación
Se seleccionaron estas operaciones porque representan las funciones principales de mantenimiento de una mascota dentro de la API: alta, consulta, modificación y baja.

Estas operaciones permiten validar un flujo CRUD completo y comprobar tanto el funcionamiento correcto de los endpoints como algunos escenarios negativos relacionados con registros inexistentes.

## Condiciones de prueba identificadas
Se consideraron las siguientes condiciones:

- Registro de una mascota con datos válidos.
- Consulta de una mascota previamente registrada.
- Modificación de los datos de una mascota existente.
- Consulta utilizando un identificador inexistente.
- Eliminación de una mascota existente.
- Verificación posterior a la eliminación para comprobar que el registro ya no pueda ser recuperado.
- Validación de códigos HTTP.
- Validación del contenido y estructura de las respuestas JSON.
- Comparación entre los datos enviados y los datos retornados por la API.

## Fuera de alcance
No se probaron las siguientes operaciones:

- Búsqueda de mascotas por estado.
- Búsqueda por tags.
- Carga de imágenes.
- Actualización mediante parámetros de formulario.
- Operaciones correspondientes a store.
- Operaciones correspondientes a user.
- Pruebas de rendimiento.
- Pruebas de seguridad.