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

 Clientes y Usuarios del Sistema
Socio / Cliente: Usuario que desea consultar la disponibilidad de pistas en tiempo real, visualizar sus reservas y comprobar el estado de su taquilla asignada.

Administrador: Personal responsable de la configuración del catálogo de pistas, gestión de tarifas por horario, registro de partes de mantenimiento y supervisión de la ocupación del centro.

 Solución Propuesta:
Desarrollar una aplicación web de gestión de reservas que permita a los clientes consultar y asegurar sus pistas en la fecha y franja horaria deseada de forma autónoma. Asimismo, el sistema proporcionará al administrador un panel de control intuitivo con una parrilla diaria de ocupación (Foto) para supervisar la disponibilidad, gestionar estados de mantenimiento y ajustar las tarifas del club.

<img width="2313" height="1899" alt="Booking - ES" src="https://github.com/user-attachments/assets/1f03e35a-d1d1-484d-aada-167c4175bade" />


## 2. Glosario de términos

Administrador: Usuario autenticado con permisos avanzados para gestionar las instalaciones, tarifas y bloqueos de mantenimiento del club. 

Mantenimiento: Estado o registro temporal asociado a una pista durante el cual queda inhabilitada para la reserva por motivos de conservación. 

Taquilla: Espacio físico de almacenamiento individual alquilado por los socios del club. 

Franja Horaria: Bloque de tiempo de duración determinada configurado por el centro deportivo para la asignación y disfrute de una pista.

Pista: Recinto o instalación deportiva delimitada y caracterizada por el deporte al que se destina (fútbol, tenis, pádel).
<img width="270" height="150" alt="image" src="https://github.com/user-attachments/assets/9383aad1-0ab8-4b20-9b2d-17dfe4aac764" />
<img width="270" height="150" alt="image" src="https://github.com/user-attachments/assets/10e46605-aa1f-49ed-8b17-f5a38abd1305" />
<img width="270" height="150" alt="image" src="https://github.com/user-attachments/assets/f3304817-f919-4bd2-9fe9-c651cbaf59ac" />

Reserva: Asignación exclusiva y anticipada de una pista a un socio para una fecha y franja horaria concretas.


## 3. Visión general del sistema
### 3.1. Requisitos generales

1. El sistema debe ser accesible vía web para socios y administradores. 

2. Se debe garantizar la integridad de las reservas impidiendo solapamientos de fechas y horas en la misma pista. 

3. El sistema mantendrá un registro histórico de las reservas e incidencias de mantenimiento finalizadas.

### 3.2. Usuarios del sistema

Administrador: Usuario con privilegios de la aplicación, al que se le permite habilitar y deshabilitar pistas. Además de asignar horarios, precios y duración de la pista. La supervisión de cancelar reservas de usuarios por incidencias del centro.

Socio: Usuario registrado que consulta pistas disponibles, revisa sus reservas y comprueba el estado de su taquilla.


## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales

R.F.01. Listar Pistas Disponibles 
Como Socio( quiero )obtener un listado de pistas disponibles filtrado por fecha, hora y tipo de superficie( para )encontrar una pista libre según mis preferencias.


R.F.02. Consultar Reservas de un Socio 
Como Socio( quiero)  visualizar mis reservas filtradas por estado (próximas, completadas o canceladas)  (para )revisar mis horarios confirmados. 



R.F.03. Consultar Parrilla Diaria de Ocupación 
Como Administrador( quiero )visualizar la parrilla completa de ocupación del club para una fecha determinada( para) supervisar el uso general del centro.



R.F.04. Listar Partes de Mantenimiento Activos 
Como Administrador ( quiero )consultar un listado de las pistas en mantenimiento con su descripción y fecha prevista de finalización( para )planificar las reparaciones del centro.


#### 4.1.1. Requisitos de información
R.I.01. Información de Usuarios 
Como Socio / Administrador( quiero )consultar los datos personales del usuario (DNI, nombre, email, teléfono y fecha de alta)( para) gestionar la identificación dentro del club.

R.I.02. Información de Pistas 
Como Socio / Administrador( quiero) consultar las características de cada pista (número, superficie, si es cubierta, con luz y precio por hora) (para) elegir la instalación adecuada. 

R.I.03. Historial de Reservas del Socio 
Como Socio quiero consultar el listado de mis reservas activas y pasadas( para )llevar un control de mis partidas e importes pagados.  

R.I.04. Ocupación Diaria de Pistas 
Como Administrador(quiero) consultar la parrilla diaria de ocupación de todas las pistas(para) conocer qué pistas están libres, reservadas o bloqueadas.

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

R.N.05. Exclusividad de Asignación de Taquilla 
Una taquilla solo puede estar alquilada por un único socio de forma activa a la vez.
Prueba 1:Asignar la Taquilla T-12 al Socio A. Intentar asignar la misma Taquilla T-12 al Socio B de forma simultánea. El sistema debe denegar la segunda asignación. 

R.N.06. Edad mínima para Reserva
Un socio debe tener al menos 16 años para efectuar una reserva de pista.
Prueba 1: Intentar registrar una reserva con la cuenta de un socio cuya fecha de nacimiento indique que tiene 15 años. El sistema debe denegar la operación e informar que no cumple el requisito de edad mínima.
Prueba 2:Intentar registrar una reserva con la cuenta de un socio que tenga 16 años o más. El sistema debe permitir la reserva con normalidad.

R.N.07. Antelación de máxima Reserva
Un socio solo puede reservar con un máximo de 14 días de antelación. Así se evita bloquear el calendario con reservas muy lejanas.
Prueba 1: Intentar reservar una pista para dentro de 30 días. El sistema debe denegarla indicando que supera el horizonte de reserva.
Prueba 2: Reservar para dentro de 7 días. La reserva debe confirmarse.
### 4.2. Mapa de historias de usuario (opcional)

### 4.3. Requisitos no funcionales (opcional)

**R.N.F. 01. Título requisito no funcional**
Como [tipo de usuario]
quiero [servicio]
para [razón]

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


