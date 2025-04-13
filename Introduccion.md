# Introduccion al Diseño Orientado a Objetos

La Programación Orientada a Objetos (POO) es un paradigma de programación basado en la organización del código en torno a "objetos", los cuales representan entidades del mundo real. Cada objeto tiene atributos (datos o propiedades) y métodos (funciones o comportamientos). Este enfoque facilita la reutilización, mantenimiento y escalabilidad del software.


* **Encapsulamiento:**
  Permite ocultar los detalles internos de un objeto y exponer solo lo necesario mediante métodos públicos, mejorando la seguridad y modularidad.

  Ejemplo del mundo real:
  
    Una cafetera. Como usuario, solo presionás un botón para hacer café. No ves cómo se calienta el agua o cómo se activa la bomba, esos detalles están ocultos.

* **Herencia:**
  Permite que una clase (subclase) herede atributos y métodos de otra clase (superclase), promoviendo la reutilización de código.

  Ejemplo del mundo real:
  
    Una clase "Vehículo" puede tener subclases como "Auto", "Moto" y "Camión". Todos los vehículos comparten características comunes, pero también tienen sus diferencias.

* **Polimorfismo:**
  Habilidad de un objeto para adoptar múltiples formas, permitiendo el uso de una misma interfaz para diferentes tipos de datos.

  Ejemplo del mundo real:
  
    Un botón "Encender" en diferentes dispositivos:

     -Enciende un televisor.

     -Enciende un ventilador.

     -Enciende una computadora.

* **Abstracción:**
  Proceso de simplificación en el cual se ocultan los detalles irrelevantes y se destacan las características esenciales de un objeto.
  
  Ejemplo del mundo real:
  
    En una app de banca móvil, el usuario solo interactúa con las funciones necesarias (consultar saldo, transferir dinero), sin ver cómo se conectan los sistemas o validan las operaciones internamente.

## Requisitos Iniciales



 * Gestión de Turnos: Permitir la asignación, modificación y cancelación de turnos médicos asegurando que no haya doble asignación en el mismo horario.

* Historial de Pacientes: Mantener un registro de turnos anteriores de cada paciente, incluyendo fechas, médicos atendidos y estado del turno.

* Disponibilidad de Médicos: Garantizar que los turnos solo puedan asignarse dentro del horario disponible de cada médico.

* Notificaciones Automáticas: Enviar alertas por correo electrónico o mensaje de texto a pacientes y médicos cuando un turno sea confirmado, modificado o cancelado.

* Seguridad y Privacidad: Asegurar que la información de pacientes y médicos esté protegida y solo accesible por personal autorizado.

## Casos de Uso

Caso de Uso 1: Registrar Paciente

Actor(es) involucrado(s):
Recepcionista

Descripción breve:
Permite registrar un nuevo paciente en el sistema con su información personal.

Flujo principal de eventos:
1. El recepcionista accede al sistema.
2. Selecciona la opción "Registrar nuevo paciente".
3. Ingresa los datos del paciente (nombre, documento, fecha de nacimiento, teléfono, correo electrónico).
4. Confirma la operación.
5. El sistema guarda la información y muestra un mensaje de éxito.

Precondiciones:
- El recepcionista debe estar autenticado en el sistema.

Postcondiciones:
- El paciente queda registrado en la base de datos y puede ser asignado a un turno.

Caso de Uso 2: Asignar Turno

Actor(es) involucrado(s):
Recepcionista, Paciente

Descripción breve:
Permite asignar un turno a un paciente con un médico disponible.

Flujo principal de eventos:
1. El recepcionista accede al sistema.
2. Selecciona la opción "Asignar turno".
3. Busca y selecciona al paciente.
4. Busca y selecciona un médico disponible en una fecha y hora específicas.
5. Ingresa el motivo de la consulta.
6. Confirma la asignación del turno.
7. El sistema guarda el turno y envía notificaciones al paciente y al médico.

Precondiciones:
- El paciente debe estar registrado en el sistema.
- Debe haber disponibilidad en la agenda del médico.

Postcondiciones:
- El turno queda registrado en el sistema.
- Se notifican el paciente y el médico.

Caso de Uso 3: Confirmar Turno

Actor(es) involucrado(s):
Paciente

Descripción breve:
Permite que un paciente confirme su asistencia a un turno programado.

Flujo principal de eventos:
1. El paciente recibe una notificación con la solicitud de confirmación.
2. Accede al sistema o responde a la notificación.
3. Confirma su asistencia al turno.
4. El sistema cambia el estado del turno a "Confirmado" y notifica al médico.

Precondiciones:
- El turno debe estar registrado en el sistema.
- El paciente debe haber recibido la notificación de confirmación.

Postcondiciones:
- El turno cambia de estado a "Confirmado".
- Se notifica al médico.

Caso de Uso 4: Cancelar Turno

Actor(es) involucrado(s):
Paciente, Médico, Recepcionista

Descripción breve:
Permite cancelar un turno programado y notificar a las partes involucradas.

Flujo principal de eventos:
1. El paciente, médico o recepcionista accede al sistema.
2. Busca el turno en la agenda.
3. Selecciona la opción "Cancelar turno".
4. Ingresa un motivo de cancelación (opcional).
5. Confirma la cancelación.
6. El sistema actualiza el estado del turno a "Cancelado" y envía notificaciones al paciente y al médico.

Precondiciones:
- El turno debe estar registrado en el sistema.
- El usuario debe tener permisos para cancelar el turno.

Postcondiciones:
- El turno queda registrado como "Cancelado".
- Se notifica al paciente y al médico.

Caso de Uso 5: Consultar Historial de Turnos

Actor(es) involucrado(s):
Recepcionista, Médico, Paciente

Descripción breve:
Permite consultar los turnos pasados y futuros de un paciente o un médico.

Flujo principal de eventos:
1. El usuario accede al sistema.
2. Selecciona la opción "Consultar historial de turnos".
3. Ingresa el nombre del paciente o médico.
4. El sistema muestra los turnos registrados con detalles (fecha, hora, estado, observaciones).

Precondiciones:
- El paciente o médico debe estar registrado en el sistema.
- El usuario debe tener permisos para acceder a esta información.

Postcondiciones:
- Se muestra el historial de turnos registrados.
