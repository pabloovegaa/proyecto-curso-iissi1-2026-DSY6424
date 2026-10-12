# Sistema de reserva de pistas

## Miembros del grupo L7-DF-6

1. Vega Ruiz, Pablo
1. González Pérez, Pablo
1. Diatta, Trevor Charles Ambroise
1. Tena Bastias, Adrian

## 1. Introducción al problema

Los centros deportivos municipales o privados cuentan con una amplia variedad de instalaciones (pistas) que se destina para el uso y disfrute de los ciudadanos.
A la hora de la gestión del acceso y asignación de pista muchas de ellas llegan a ser manuales o poco coordinadas. Dificultando la organizacion y el aprovechamiento optimo de las pistas.
Entre los problemas encontrados podemos ver:
- Una desorganización y conflictos de horario: Falta una centralización que evite la asignacion de una pista a dos clientes diferentes.
- Falta de visibilidad: Imposibilidad de los clientes para ver cuales plazas están libres.
- Carga administrativa: Dificultad del personal para actualizar precios, habilitar o deshabilitar pistas.
Usuarios:
-Cliente: Usuario que quiere ver las pistas disponibles y reservar la instalación en una franja horaria determinada.
-Administrador: Personal responsable de la configuración de pistas, gestión de precios, dar alta/baja pistas y una supervisión del sistema.
Solucion:
Desarrollar una aplicación de gestión de reservas que permita a los clientes seleccionar y asegurar su pista en la fecha y franja horaria deseada de forma autónoma. Asimismo, la herramienta proporcionará al administrador un panel de control intuitivo para gestionar el catálogo de pistas, establecer sus precios y ajustar la disponibilidad según la operativa del centro deportivo.
<img width="2313" height="1899" alt="Booking - ES" src="https://github.com/user-attachments/assets/1f03e35a-d1d1-484d-aada-167c4175bade" />


## 2. Glosario de términos

Franja Horaria: Bloque de tiempo de duración determinada configurado por el centro deportivo para la asignación y disfrute de una pista.

Pista: Recinto o instalación deportiva delimitada y caracterizada por el deporte al que se destina (fútbol, tenis, pádel).

Reserva: Asignación exclusiva y anticipada de una pista a un socio para una fecha y franja horaria concretas.


## 3. Visión general del sistema

### 3.1. Requisitos generales

### 3.2. Usuarios del sistema
Administrador: Usuario con privilegios de la aplicación, al que se le permite habilitar y deshabilitar pistas. Además de asignar horarios, precios y duración de la pista. La supervisión de cancelar reservas de usuarios por incidencias del centro.

Cliente: Usuario registrado en la aplicación que tiene disponibilidad de consultar pistas alquiladas, la posibilidad de reservar, gestionar o cancelar reserva de pista.

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


