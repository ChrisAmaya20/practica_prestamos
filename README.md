# Practica de prestamos de equipo UNICAH

Nombre: Christopher Jose Amaya Pineda
Numero de cuenta: PENDIENTE

## Respuestas

## Respuestas de la práctica

### Paso 1. Catálogo de equipos

1. Al desmarcar Activo, el equipo queda archivado y deja de aparecer normalmente en los listados. Es mejor que borrarlo porque se conserva su información.

2. copy=False evita que el código de inventario se copie automáticamente cuando se duplica un equipo.

### Paso 2. Registro de préstamos

1. _name crea el modelo de préstamos y _inherit permite utilizar las funciones de mail.thread para registrar mensajes.

2. tracking=True permite guardar en el historial los cambios del estado del préstamo.

### Paso 3. Equipos del préstamo

1. prestamo.linea indica el modelo relacionado y prestamo_id es el campo que conecta cada línea con su préstamo.

2. Al borrar un préstamo también se eliminan sus líneas. Esto se define con ondelete="cascade".

### Paso 4. Flujo de estados

1. Los métodos también validan el estado porque ocultar botones no es suficiente para proteger los datos. La validación evita operaciones incorrectas.

2. write cambia el estado de todos los equipos relacionados. No necesitamos un for porque Odoo permite actualizar varios registros juntos.

### Paso 5. Reglas del préstamo

1. Aunque el campo filtre los equipos disponibles, necesitamos otra validación porque el estado de un equipo puede cambiar antes de confirmar el préstamo.

2. @api.constrains se ejecuta al crear o modificar los campos correspondientes. La validación de action_prestar se ejecuta cuando presionamos el botón Prestar.

### Paso 6. Contacto, kanban y búsqueda

1. Al mover una tarjeta a otra columna, Odoo puede cambiar el estado del equipo porque las columnas están agrupadas por ese campo.

2. No se crea una columna nueva en contactos. One2many utiliza la relación existente mediante partner_id en el modelo de préstamos.
