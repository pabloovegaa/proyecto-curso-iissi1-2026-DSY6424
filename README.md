# Sistema de reserva de pistas

## Miembros del grupo L7-DF-6

1. Vega Ruiz, Pablo
1. González Pérez, Pablo
1. Diatta, Trevor Charles Ambroise
1. Tena Bastías, Adrián

## 1. Introducción al problema

Los centros deportivos municipales y privados cuentan con una amplia variedad de instalaciones deportivas (principalmente pistas de pádel y tenis) destinadas al uso y disfrute de sus socios y clientes. En la actualidad, la gestión del acceso, el control de mantenimiento y la asignación de estas pistas se realizan de forma manual o mediante sistemas poco coordinados (llamadas telefónicas y anotaciones en papel), lo que dificulta la organización y el aprovechamiento óptimo de las instalaciones.

Entre los principales problemas detectados en la situación actual destacan:

Desorganización y conflictos de horario:Ausencia de un sistema centralizado que evite la asignación doble de una misma pista a dos clientes en la misma franja horaria.

Falta de visibilidad e ineficiencia: Imposibilidad de los usuarios para consultar en tiempo real qué pistas y franjas horarias se encuentran libres u ocupadas.

Carga administrativa y falta de control de instalaciones: Dificultad del personal del club para gestionar tarifas, registrar bloqueos de pistas por mantenimiento o controlar la asignación de servicios adicionales como las taquillas.


 Solución Propuesta:
Desarrollar una aplicación web de gestión de reservas que permita a los clientes consultar y asegurar sus pistas en la fecha y franja horaria deseada de forma autónoma. Asimismo, el sistema proporcionará al administrador un panel de control intuitivo con una parrilla diaria de ocupación (Foto) para supervisar la disponibilidad, gestionar estados de mantenimiento y ajustar las tarifas del club.



## 2. Glosario de términos


## 3. Visión general del sistema
### 3.1. Requisitos generales

RG.01. Control de acceso por roles.

Como usuario del sistema (Socio o Administrador) quiero autenticarme para acceder solo a las funciones propias de mi rol para proteger la información y garantizar un uso adecuado del sistema.


RG.02 Sistema de pistas. 

Como administrador quiero gestionar las pistas del club y consultar su ocupación; como socio quiero consultar las pistas disponibles. 

RG.03 Sistema de reservas. 

Como socio quiero gestionar mis reservas de pistas. 

RG.04 Sistema de mantenimientos. 

Como administrador quiero gestionar los mantenimientos de las pistas. 

RG.05 Sistema de taquillas. 

Como administrador quiero gestionar las taquillas del club y su asignación a los socios.

### 3.2. Usuarios del sistema

Administrador: Usuario que gestiona las instalaciones y supervisa las reservas del club.


Socio: Usuario que reserva pistas y consulta sus reservas y su taquilla.

## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales

RF2.1 Listado de pistas 

Como Administrador, quiero ver un listado de las pistas con su número, superficie, si es cubierta, si tiene luz, precio por hora y estado, para conocer las instalaciones del club.

Prueba de aceptación:

Acceder a la pantalla Pistas. Se muestra una tabla con todas las pistas y los botones Nueva pista, Editar, Eliminar y Habilitar/Deshabilitar.

Acceder con una sesión de socio. El sistema deniega el acceso a la pantalla.

RF2.2 Creación de pistas

Como Administrador, quiero dar de alta una pista indicando su número, superficie, si es cubierta, si tiene luz y su precio por hora, para ampliar las instalaciones disponibles.

Prueba de aceptación:

Pulsar Nueva pista, rellenar todos los datos y pulsar Guardar. La pista aparece en el listado con estado habilitada. 

Introducir un número de pista ya existente y pulsar Guardar. El sistema rechaza el alta e informa de que el número existe.

Introducir un precio negativo o vacío y pulsar Guardar. El sistema muestra un error de validación y no guarda.

Pulsar Cancelar. Se vuelve al listado sin crear la pista.

RF2.3 Edición de pistas 

Como Administrador, quiero modificar las características de una pista (superficie, cubierta, luz, precio por hora), para mantener sus datos actualizados. 

Prueba de aceptación

Pulsar Editar, cambiar el precio por hora y pulsar Guardar cambios. El listado muestra el nuevo precio.

Vaciar la superficie y pulsar Guardar cambios. El sistema muestra un error de validación y no guarda.

Cambiar el precio de una pista con reservas ya confirmadas. Las reservas existentes conservan el precio con el que se hicieron.

RF2.4 Eliminación de pistas 

Como Administrador, quiero eliminar una pista, para retirar del sistema las que ya no existen.

Prueba de aceptación

Pulsar Eliminar sobre una pista sin reservas futuras ni mantenimiento activo y pulsar Confirmar. La pista desaparece del listado. 

Pulsar Eliminar y después Cancelar. La pista permanece en el listado.

Pulsar Eliminar sobre una pista con reservas futuras activas o un parte de mantenimiento activo. El sistema impide la eliminación e informa del motivo.


RF5.1 Listado de taquillas 

Como administrador, quiero ver un listado de las taquillas con su código, ubicación, estado y socio asignado, para saber cuáles están libres.

Prueba de aceptación:

Acceder a la pantalla Taquillas. Se muestra una tabla con todas las taquillas y los botones Nueva taquilla, Editar, Eliminar, Asignar y Liberar.

Acceder con una sesión de socio. El sistema deniega el acceso a la pantalla.

RF5.2 Creación de taquillas 

Como administrador, quiero dar de alta una taquilla indicando su código y ubicación, para ampliar las taquillas disponibles del club. 

Prueba de aceptación:

Pulsar Nueva taquilla, rellenar código y ubicación y pulsar Guardar. La taquilla aparece en el listado con estado libre. 

Introducir un código ya existente y pulsar Guardar. El sistema rechaza el alta e informa de que el código existe. 

Pulsar Cancelar. Se vuelve al listado sin crear la taquilla.

RF5.3 Edición de taquillas Como administrador, quiero modificar el código o la ubicación de una taquilla, para corregir sus datos. 

Prueba de aceptación:

Pulsar Editar, cambiar la ubicación y pulsar Guardar cambios. El listado muestra la nueva ubicación. 

Vaciar el código y pulsar Guardar cambios. El sistema muestra un error de validación y no guarda.

RF5.4 Eliminación de taquillas Como administrador, quiero eliminar una taquilla, para retirar del sistema las que ya no existen. 

Prueba de aceptación:

Pulsar Eliminar sobre una taquilla libre y pulsar Confirmar. La taquilla desaparece del listado. 

Pulsar Eliminar y después Cancelar. La taquilla permanece en el listado. 

Pulsar Eliminar sobre una taquilla con alquiler activo. El sistema impide la eliminación e informa del motivo.

#### 4.1.1. Requisitos de información
R.I.01. Información de Usuarios 
Como Socio / Administrador **quiero** consultar los datos personales del usuario (DNI, nombre, email, teléfono y fecha de alta) **para** gestionar la identificación dentro del club.

R.I.02. Información de Pistas 
Como Socio / Administrador **quiero** consultar las características de cada pista (número, superficie, si es cubierta, con luz y precio por hora) **para** elegir la instalación adecuada. 

R.I.03. Historial de Reservas del Socio 
Como Socio **quiero** consultar el listado de mis reservas activas y pasadas **para** llevar un control de mis partidas e importes pagados.  

R.I.04. Ocupación Diaria de Pistas 
Como Administrador **quiero** consultar la parrilla diaria de ocupación de todas las pistas **para** conocer qué pistas están libres, reservadas o bloqueadas.

#### 4.1.2. Reglas de negocio
R.N.01. Exclusividad de Reserva por Pista 
Una pista sólo puede tener una única reserva activa en la misma fecha y franja horaria. 

Prueba 1: Intentar registrar una reserva para la Pista 1 el 20/10/2026 a las 10:00 h habiendo ya una reserva confirmada en ese tramo. El sistema debe bloquear la operación e informar de un conflicto de ocupación. 

Prueba 2: Solicitar reserva para la Pista 1 en un tramo posterior (11:30 h) del mismo día. Comprobar que el sistema confirma la reserva correctamente.

R.N.02. Límite de Reservas Activas por Socio 
Un socio no puede tener más de 2 reservas activas simultáneas en el sistema para evitar el acaparamiento de pistas. 

Prueba 1:Seleccionar un socio que posea 2 reservas activas para días futuros e intentar asignarle una 3ª reserva. El sistema debe denegar la acción indicando que ha alcanzado el límite máximo. 

Prueba 2: Proceder a cancelar una de las dos reservas del socio e intentar de nuevo registrar la reserva. Comprobar que la operación resulta exitosa.

R.N.03. Antelación Mínima para Cancelación
Una reserva solo puede ser cancelada sin coste económico si se solicita con un mínimo de 12 horas de antelación respecto al inicio del horario reservado.

Prueba 1:Cancelar una reserva programada para las 20:00 h solicitándolo a las 07:00 h del mismo día (13 h de antelación). Comprobar que se procesa sin penalización.

Prueba 2:Intentar cancelar la misma reserva a las 12:00 h (8 h de antelación). Comprobar que el sistema deniega la devolución por incumplimiento de antelación.

R.N.04. Incompatibilidad por Mantenimiento 
Una pista marcada con un registro de mantenimiento activo en un horario determinado no puede ser reservada por ningún socio.  

Prueba 1:Solicitar disponibilidad de la Pista 3 durante una fecha y hora en la que tiene registrado un parte de mantenimiento. La Pista 3 no debe aparecer en el listado de pistas disponibles. 


Prueba 2: Registrar un mantenimiento para la Pista 3 el 20/10/2026 de 10:00 h a 12:00 h. Consultar la disponibilidad de esa pista a las 13:00 h del mismo día. La Pista 3 debe aparecer en el listado de pistas disponibles.


R.N.05. Exclusividad de Asignación de Taquilla 
Una taquilla solo puede estar alquilada por un único socio de forma activa a la vez.

Prueba 1:Asignar la Taquilla T-12 al Socio A. Intentar asignar la misma Taquilla T-12 al Socio B de forma simultánea. El sistema debe denegar la segunda asignación. 

Prueba 2:Asignar la Taquilla T-12 al Socio A y después liberarla (finalizar su alquiler). Asignar la Taquilla T-12 al Socio B. El sistema debe permitir la asignación.

R.N.06. Antelación de máxima Reserva
Un socio solo puede reservar con un máximo de 14 días de antelación. Así se evita bloquear el calendario con reservas muy lejanas.

Prueba 1: Intentar reservar una pista para dentro de 30 días. El sistema debe denegarla indicando que supera el horizonte de reserva.

Prueba 2: Reservar para dentro de 7 días. La reserva debe confirmarse.


### 4.2. Mapa de historias de usuario (opcional)

### 4.3. Requisitos no funcionales (opcional)

**R.N.F. 01. Título requisito no funcional**
Como [tipo de usuario]
quiero [servicio]
para [razón]

R.N.F.01. Rendimiento: Como Socio quiero que el listado de pistas disponibles se muestre en menos de 3 segundos para poder reservar con rapidez. 

R.N.F.02. Usabilidad: Como Socio quiero poder completar una reserva en un máximo de 4 pasos para no necesitar formación previa.  

R.N.F.03. Disponibilidad: Como Administrador quiero que el sistema esté disponible el 99 % del tiempo para que los socios puedan reservar a cualquier hora.  

R.N.F.04. Seguridad: Como Socio quiero que el acceso requiera autenticación y que mis datos personales solo sean visibles para mí y para el administrador para proteger mi privacidad. 

R.N.F.05. Protección: de datos Como Administrador quiero que el sistema cumpla el RGPD en el tratamiento de los datos personales (DNI, email, teléfono) para evitar incumplimientos legales.  

R.N.F.06. Concurrencia: Como Socio quiero que el sistema soporte varios usuarios reservando a la vez sin generar reservas duplicadas para que la integridad de las reservas se mantenga.  

R.N.F.07. Compatibilidad: Como Socio quiero acceder desde los navegadores actuales (Chrome, Firefox, Edge, Safari) y desde móvil para reservar desde cualquier dispositivo.

R.N.F.08. Persistencia/Copias de seguridad: Como Administrador quiero que se realice una copia de seguridad diaria de los datos para no perder el histórico de reservas y mantenimientos

-- fin entregable 1 --

## 5. Modelo conceptual

### 5.1. Diagramas de clases UML

- con restricciones.

### 5.2. Escenarios de prueba

- con descripción textual y diagrama de objetos UML.

## 6. Matrices de trazabilidad

- Matriz de trazabilidad entre los elementos del modelo conceptual y los requisitos.

|       | EntidadX   | AsociaciónX  | RestricciónX  | Entidad2 ...   | 
|:------|:-----------|:-----------|:-----------|:-----------|
| RI-1  | X          | X          | X          | X          |
| RI-2  |            | X          |            | X          |
| RF-1  |            | X          |            | X          |
| RF-2  | X          |            | X          | X          |
| RN-1  |            | X          |            |            |
| RN-2  | X          | X          | X          |            |
| ...   |            |            |            |            |

-- fin entregable 2 --

## 7. Modelo relacional en 3FN

- Relaciones obtenidas al aplicar la transformación del modelo conceptual.

### 7.1.  Justificación de la estrategia de transformación de jerarquías

- si se identificaron jerarquías en el MC.


### 8. Matriz de trazabilidad MC/SQL (opcional):

- Restricciones sobre el MC / Elementos del modelo tecnológico (SQL) (Triggers, checks, etc.)
- Incluir Reglas de negocio — Constraints/Triggers en las matrices de trazabilidad para el entregable 3

|       | EntidadX   | AsociaciónX  | RestricciónX  | Entidad2 ...   | 
|:-------|:-------|:-------|:-------|:-------|
| TABLA-1 |        |        |        |        |
| TABLA-2 |        |        |        |        |
| TABLA-3 |        |        |        |        |
| TABLA-4 |        |        |        |        |
| TRIG-1 |        |        |        |        |
| TRIG-2 | X      | X      |        | X      |
| TRIG-3 |        | X      |        | X      |
| TRIG-4 |        |        | X      |        |
| CONST-1 |        |        |        |        |
| CONST-2 | X      | X      |        | X      |
| CONST-3 |        | X      |        | X      |
| CONST-4 |        |        | X      |        |

Se consideran todo tipo de constraints declarativas (aquellas definidas durante el CREATE TABLE).
-- fin entregable 3 --

## Referencias


