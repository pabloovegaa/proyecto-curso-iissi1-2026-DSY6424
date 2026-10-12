# Sistema de reserva de pistas

## Miembros del grupo L7-DF-6

1. Vega Ruiz, Pablo
1. González Pérez, Pablo
1. Diatta, Trevor Charles Ambroise
1. Tena Bastias, Adrian

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

 Socio: Usuario registrado en la plataforma habilitado para realizar consultas de disponibilidad y solicitar alquileres de pistas o taquillas. 

Taquilla: Espacio físico de almacenamiento individual alquilado por los socios del club. 

Franja Horaria: Bloque de tiempo de duración determinada configurado por el centro deportivo para la asignación y disfrute de una pista.

Pista: Recinto o instalación deportiva delimitada y caracterizada por el deporte al que se destina (fútbol, tenis, pádel).

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

#### R.F.01. Título requisito funcional

Como [tipo de usuario]
quiero [servicio]
para [razón]

**Prueba de aceptación**
- Descripción de la primera comprobación a realizar
- Descripción de la segunda comprobación a realizar
- Se debe aplicar la regla de negocio R.N.XX.
- ...

#### 4.1.1. Requisitos de información

##### R.I.01. Título requisito de información

Como [tipo de usuario]
quiero [servicio]
para [razón]

**Prueba de aceptación**
- Descripción de la primera comprobación a realizar
- Descripción de la segunda comprobación a realizar
- ...

#### 4.1.2. Reglas de negocio

##### R.N.01. Título regla negocio

Descripción de la regla de negocio.

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


