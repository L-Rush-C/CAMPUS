# Historias de usuario

Las prioridades marcadas son una propuesta basada en el impacto de cada función. El Excel no incluye una columna de prioridad.

## HU-001: Gestionar residentes
**Como** administrador
**Quiero** gestionar los residentes
**Para** mantener un censo actualizado y controlar la ocupación de la copropiedad.

**Criterios de aceptación:**
- [ ] Registrar un residente.
- [ ] Editar la información de un residente.
- [ ] Eliminar el registro de un residente.

**Prioridad:** Alta

## HU-002: Gestionar visitantes
**Como** administrador
**Quiero** gestionar los visitantes
**Para** garantizar el control de acceso y reforzar la seguridad en el ingreso.

**Criterios de aceptación:**
- [ ] Registrar un visitante.
- [ ] Editar la información de un visitante.
- [ ] Eliminar el registro de un visitante.

**Prioridad:** Alta

## HU-003: Gestionar usuarios de C.A.M.P.U.S
**Como** administrador
**Quiero** gestionar los usuarios que trabajan en el conjunto
**Para** administrar roles, simplificar procesos y asignar permisos al personal.

**Criterios de aceptación:**
- [ ] Registrar usuarios.
- [ ] Editar la información de los usuarios.
- [ ] Eliminar usuarios.
- [ ] Controlar los permisos de acceso de cada usuario en la plataforma.

**Prioridad:** Alta

## HU-004: Gestionar torres, pisos y apartamentos
**Como** administrador
**Quiero** gestionar la información de torres, pisos y apartamentos
**Para** simplificar los procesos y mantener la información organizada.

**Criterios de aceptación:**
- [ ] Registrar torres, pisos y apartamentos.
- [ ] Editar la información de torres, pisos y apartamentos.
- [ ] Eliminar torres, pisos y apartamentos.

**Prioridad:** Alta

## HU-005: Gestionar zonas comunes
**Como** administrador
**Quiero** gestionar la información de las zonas disponibles para reservar
**Para** optimizar la reserva de espacios comunes y controlar su disponibilidad.

**Criterios de aceptación:**
- [ ] Registrar una zona.
- [ ] Editar una zona.
- [ ] Eliminar una zona.
- [ ] Visualizar las solicitudes de reserva de zonas.
- [ ] Aceptar o rechazar solicitudes de reserva de zonas.

**Prioridad:** Alta

## HU-006: Gestionar vehículos y parqueaderos
**Como** administrador
**Quiero** gestionar los vehículos que ingresan al conjunto y sus parqueaderos
**Para** controlar el parqueadero, mantener el inventario vehicular y regular el acceso.

**Criterios de aceptación:**
- [ ] Registrar vehículos.
- [ ] Crear y eliminar reservas de parqueadero.
- [ ] Editar y eliminar vehículos.
- [ ] Asignar, eliminar y consultar la información del parqueadero de un vehículo.

**Prioridad:** Alta

## HU-007: Gestionar reportes
**Como** administrador
**Quiero** gestionar las solicitudes de reportes
**Para** dar seguimiento a las solicitudes y agilizar la toma de decisiones.

**Criterios de aceptación:**
- [ ] Visualizar un reporte.
- [ ] Aceptar o rechazar un reporte.
- [ ] Consultar reportes anteriores.
- [ ] Eliminar reportes anteriores.

**Prioridad:** Alta

## HU-008: Gestionar registros de bicicletas
**Como** administrador
**Quiero** gestionar las bicicletas registradas
**Para** identificar la propiedad de los vehículos no motorizados y prevenir extravíos.

**Criterios de aceptación:**
- [ ] Registrar bicicletas.
- [ ] Editar la información de las bicicletas.
- [ ] Eliminar bicicletas.

**Prioridad:** Media

## HU-009: Gestionar pagos mediante lista de chequeo
**Como** administrador
**Quiero** gestionar la información de pagos
**Para** llevar un registro claro del estado de cuenta.

**Criterios de aceptación:**
- [ ] Visualizar la información de pagos.
- [ ] Consultar la lista de chequeo.
- [ ] Marcar y desmarcar pagos.

**Prioridad:** Alta

## HU-010: Publicar comunicados
**Como** administrador
**Quiero** crear y publicar anuncios, circulares o mantenimientos programados
**Para** mantener informada a la comunidad y agilizar la difusión de avisos importantes.

**Criterios de aceptación:**
- [ ] Subir imágenes para acompañar un comunicado.
- [ ] Escribir el título del comunicado.
- [ ] Publicar el comunicado.
- [ ] Eliminar comunicados antiguos.

**Prioridad:** Alta

## HU-011: Reservar zonas para eventos
**Como** residente
**Quiero** reservar una zona para un evento
**Para** realizar actividades en los espacios comunes del conjunto.

**Criterios de aceptación:**
- [ ] Consultar los horarios y las zonas disponibles.
- [ ] Realizar una solicitud de reserva de zona.
- [ ] Recibir la justificación y la confirmación o negación de la solicitud.

**Prioridad:** Alta

## HU-012: Reportar daños
**Como** residente
**Quiero** comunicar un daño a la administración
**Para** que los administradores puedan conocerlo y solucionarlo.

**Criterios de aceptación:**
- [ ] Realizar una solicitud de reporte de daño.
- [ ] Eliminar un reporte propio.
- [ ] Visualizar los reportes enviados.

**Prioridad:** Alta

## HU-013: Visualizar la cartelera virtual
**Como** residente
**Quiero** ver los comunicados emitidos por la administración en una sección dedicada
**Para** enterarme de las novedades del conjunto sin acudir a la cartelera física.

**Criterios de aceptación:**
- [ ] Visualizar en la página de inicio los últimos anuncios publicados.
- [ ] Cargar los anuncios de forma ordenada.

**Prioridad:** Media

## HU-015: Gestionar la asistencia de visitantes
**Como** administrador
**Quiero** simplificar el proceso de registro de visitas
**Para** evitar problemas al momento de permitir el ingreso.

**Criterios de aceptación:**
- [ ] Crear un registro de asistencia.
- [ ] Editar un registro de asistencia.
- [ ] Eliminar un registro de asistencia.

**Prioridad:** Alta

> Nota: el Excel no contiene una historia identificada como HU-014.

---

## Requisitos no funcionales
Estos requisitos describen las condiciones de calidad, seguridad y operación que debe cumplir el sistema, independientemente de una funcionalidad específica.

| Requisito | Descripción | Criterio medible |
|---|---|---|
| Rendimiento | Las operaciones principales deben responder rápidamente bajo carga normal. | Registrar, consultar, actualizar y eliminar información debe responder en máximo 3 segundos bajo carga normal. |
| Seguridad | El sistema debe proteger las cuentas, la información y las funciones según el rol del usuario. | Debe usar autenticación, contraseñas protegidas, permisos por rol, HTTPS y control de acceso. |
| Usabilidad | La interfaz debe ser clara, sencilla y adaptable a los dispositivos de la comunidad. | Las vistas principales deben funcionar en computadores, tabletas y celulares sin requerir un manual para las tareas habituales. |
| Disponibilidad | La plataforma debe estar disponible durante la operación habitual del conjunto y permitir recuperar la información. | Deben realizarse copias de seguridad periódicas y mantenerse el servicio disponible la mayor parte del tiempo. |
| Integridad | La información registrada debe ser válida, consistente y no duplicada. | El sistema debe validar los datos obligatorios y rechazar registros duplicados o inconsistentes. |
| Mantenibilidad | El sistema debe facilitar la corrección, evolución y administración del código. | El código debe estar organizado por módulos y administrarse mediante control de versiones en Git/GitHub. |