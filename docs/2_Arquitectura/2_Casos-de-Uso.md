# Casos de uso

## Diagrama de casos de uso

![Diagrama de casos de uso](/home/nollt/Documentos/CAMPUS/docs/2_Arquitectura/C-USOS.jpeg)
<!-- Exportado desde [StarUML / Draw.io / Lucidchart — el que usen] -->

## Documentación de casos de uso (formato extendido)

### CU-01: [Nombre del caso de uso]
| Campo            | Descripción                                  |
|------------------|----------------------------------------------|
| Actor(es)        | [Quién ejecuta la acción]                    |
| Precondición     | [Qué debe cumplirse antes]                   |
| Flujo principal  | 1. ...<br>2. ...<br>3. ...                   |
| Flujos alternos  | [Qué pasa si algo falla o se desvía]         |
| Postcondición    | [Estado del sistema al terminar]             |

### CU-01: Gestión de residentes
| Campo            | Descripción                                  |
|------------------|----------------------------------------------|
| Actor(es)        | Administración                               |
| Precondición     | El usuario de la administración debe haber iniciado sesión con credenciales de administrador en la plataforma C.A.M.P.U.S. |
| Flujo principal  | 1. El Administrador ingresa al módulo "Gestión de residentes". El sistema despliega el listado completo de residentes registrados con sus respectivas opciones.<br>2. El Administrador selecciona la acción a realizar: Registrar, Editar o Borrar un residente. El sistema presenta el cuadro de diálogo correspondiente a la acción seleccionada y ejecuta el módulo "Residente ya registrado" para verificar si el usuario ya existe en la base de datos.<br>3. El Administrador diligencia o modifica la información requerida. El sistema valida que los campos obligatorios estén completos y en el formato correcto.<br>4. El Administrador confirma y guarda la operación. El sistema almacena o actualiza la información en la base de datos, muestra un mensaje de confirmación y refresca el listado. |
| Flujos alternos  | **2A:** El Administrador intenta registrar un residente con una identificación o correo ya existente. El sistema notifica que el residente ya está registrado y bloquea el guardado para evitar duplicados.<br>**4A:** El Administrador intenta guardar el formulario con datos faltantes o incorrectos. El sistema resalta los campos erróneos e impide el guardado hasta corregir los datos. |
| Postcondición    | La información del residente queda registrada, actualizada o eliminada/deshabilitada correctamente en la base de datos del conjunto habitacional. |


### CU-02: Gestión de visitantes
| Campo            | Descripción                                  |
|------------------|----------------------------------------------|
| Actor(es)        | Administración                               |
| Precondición     | El usuario de la administración debe haber iniciado sesión con credenciales válidas en la plataforma C.A.M.P.U.S. |
| Flujo principal  | 1. El Administrador ingresa al módulo "Gestión de visitantes". El sistema despliega el listado de visitantes e historial de asistencias recientes con opciones de búsqueda y filtrado.<br>2. El Administrador selecciona la acción a realizar: Registrar visitante, Editar visitante, Borrar visitante o Gestión de Asistencias. El sistema presenta el formulario o panel correspondiente según la acción seleccionada.<br>3. El Administrador ingresa el documento de identidad o datos del visitante. El sistema ejecuta la validación "Visitante ya registrado" para comprobar si los datos ya existen en la base de datos.<br>4. El Administrador completa los datos del visitante (nombre, cédula, teléfono, vehículo si aplica, torre/apto a visitar) y/o registra el ingreso en Asistencias. El sistema valida la completitud de los campos requeridos y el formato de la información.<br>5. El Administrador guarda la operación o confirma el registro de ingreso/asistencia. El sistema almacena la información, registra la hora exacta de ingreso/asistencia, genera la confirmación en pantalla y actualiza la lista en tiempo real. |
| Flujos alternos  | **3A:** El Administrador ingresa el documento de un visitante que ya existe en el sistema. El sistema carga automáticamente sus datos personales previos para agilizar el registro de asistencia sin necesidad de digitar todo de nuevo.<br>**4A:** El Administrador intenta guardar el registro omitiendo información obligatoria. El sistema resalta los campos faltantes e impide completar el registro de asistencia hasta corregirlos.<br>**2B:** El Administrador solicita eliminar un registro de visitante o un historial de asistencia. El sistema emite un mensaje de advertencia y solicita confirmación. El Administrador confirma la acción. El sistema elimina o inhabilita el registro en la base de datos y actualiza la vista. |
| Postcondición    | La información del visitante y su historial de asistencia/ingreso quedan guardados o actualizados correctamente en la base de datos. |



### CU-03: Gestión de usuarios
| Campo            | Descripción                                  |
|------------------|----------------------------------------------|
| Actor(es)        | Administración                               |
| Precondición     | El usuario de la administración debe haber iniciado sesión con credenciales válidas en la plataforma C.A.M.P.U.S. |
| Flujo principal  | 1. El Administrador ingresa al módulo "Gestión de usuarios". El sistema despliega el listado completo de trabajadores y usuarios del sistema.<br>2. El Administrador selecciona la acción a realizar: Registrar usuario, Editar usuario, Borrar usuario o Controlar accesos de usuarios. El sistema presenta el formulario o panel de permisos correspondiente según la acción seleccionada.<br>3. El Administrador diligencia o modifica los datos del usuario y configura sus permisos de acceso en C.A.M.P.U.S. El sistema ejecuta el módulo "Usuario ya creado" para verificar si la cuenta ya existe en la base de datos.<br>4. El Administrador confirma y guarda la operación. El sistema almacena la cuenta, guarda la configuración de permisos, emite un mensaje de éxito y refresca el listado de usuarios. |
| Flujos alternos  | **3A:** El Administrador intenta registrar un usuario con un documento o correo ya registrado. El sistema notifica que el usuario ya existe en la plataforma y detiene la creación para evitar duplicados.<br>**4A:** El Administrador intenta guardar sin seleccionar un rol o dejando datos obligatorios vacíos. El sistema resalta los campos faltantes e impide guardar hasta que se completen adecuadamente.<br>**2B:** El Administrador selecciona la opción de eliminar o inhabilitar a un trabajador. El sistema solicita confirmación advirtiendo sobre la revocación de credenciales. El Administrador confirma la acción. El sistema desactiva la cuenta, inhabilita el acceso al sistema C.A.M.P.U.S. y actualiza la lista. |
| Postcondición    | El usuario queda registrado, modificado, inhabilitado o con sus permisos de acceso actualizados en la base de datos. |



### CU-04: Gestionar torres
| Campo            | Descripción                                  |
|------------------|----------------------------------------------|
| Actor(es)        | Administración                               |
| Precondición     | El usuario de la administración debe haber iniciado sesión con credenciales válidas en la plataforma C.A.M.P.U.S. |
| Flujo principal  | 1. El Administrador ingresa al módulo "Gestión torres-pisos-apartamentos". El sistema despliega el árbol de la estructura física del conjunto (Torres creadas, pisos y lista de apartamentos por piso).<br>2. El Administrador selecciona la acción a realizar: Registrar torre-piso-apto, Editar torre-piso-apto o Borrar torre-piso-apto. El sistema presenta el formulario o panel jerárquico según el nivel seleccionado (Torre, Piso o Apartamento).<br>3. (Creación de Torre y pisos) El Administrador ingresa el identificador/nombre de la Torre y define la cantidad de pisos. El sistema genera la estructura de la torre y habilita la creación de pisos asociados.<br>4. (Creación de Apartamentos) El Administrador selecciona un piso específico e ingresa la numeración de los apartamentos pertenecientes a dicho piso. El sistema valida que la nomenclatura de los apartamentos sea única en esa torre/piso y que los campos numéricos sean válidos.<br>5. El Administrador confirma y guarda la estructura creada o modificada. El sistema almacena la jerarquía en la base de datos, muestra un mensaje de confirmación y actualiza el árbol del conjunto. |
| Flujos alternos  | **A1:** El Administrador intenta registrar o renombrar una torre o apartamento con un identificador ya existente. El sistema notifica la duplicidad e impide el guardado hasta ingresar un código único. |
| Postcondición    | La estructura física (torres, pisos y apartamentos) queda creada, actualizada o deshabilitada en la base de datos de C.A.M.P.U.S. |



### CU-05: Gestión de reservas de zonas
| Campo            | Descripción                                  |
|------------------|----------------------------------------------|
| Actor(es)        | Administración                               |
| Precondición     | El usuario de la administración debe haber iniciado sesión con credenciales de Administrador en la plataforma C.A.M.P.U.S. y deben existir zonas parametrizadas o solicitudes enviadas por los residentes. |
| Flujo principal  | 1. El Administrador ingresa al módulo "Gestión de zonas". El sistema despliega el catálogo de zonas comunes registradas, el calendario de disponibilidad y la bandeja de solicitudes de reserva pendientes.<br>2. El Administrador selecciona la acción a realizar: Registrar zona, Editar zona, Borrar zona, Ver solicitud de zonas o Aceptar/Rechazar solicitudes. El sistema presenta el formulario de parametrización de zona o el listado detallado de solicitudes según la opción elegida.<br>3. El Administrador completa o modifica los datos del área común. El sistema valida que los campos estén completos, guarda los parámetros en la base de datos y actualiza el catálogo visible para los residentes.<br>4. El Administrador selecciona una solicitud pendiente de la lista y ejecuta la acción "Aceptar solicitudes de zonas". El sistema muestra los detalles de la reserva (residente, fecha, horario, comprobante) y solicita confirmación.<br>5. El Administrador confirma la aprobación de la reserva. El sistema cambia el estado de la reserva a "Aprobada", bloquea definitivamente el cupo/horario en el calendario para evitar cruces y notifica la confirmación al residente. |
| Flujos alternos  | **4A:** El Administrador selecciona "Rechazar solicitud de zona" sobre una solicitud e ingresa el motivo de la negativa. El sistema cambia el estado a "Rechazada", libera el rango de fecha/hora en el calendario para otros residentes y notifica la razón al usuario.<br>**3A:** El Administrador intenta guardar una zona dejando campos obligatorios vacíos (nombre, aforo) o con horarios incoherentes. El sistema marca los campos faltantes e impide el guardado hasta que se corrijan los datos.<br>**2B:** El Administrador solicita eliminar una zona común del catálogo. El sistema verifica si existen reservas activas/futuras en dicha zona. Si existen, muestra un aviso advirtiendo que debe gestionarlas antes de eliminar. |
| Postcondición    | La zona común queda creada/modificada en el catálogo o el estado de la reserva solicitada cambia a "Aprobada" / "Rechazada", actualizando el calendario y notificando al residente. |



### CU-06: Gestión vehiculos
| Campo            | Descripción                                  |
|------------------|----------------------------------------------|
| Actor(es)        | Administración                               |
| Precondición     | El usuario de la administración debe haber iniciado sesión con credenciales válidas en la plataforma C.A.M.P.U.S. y deben existir residentes u apartamentos registrados en el sistema. |
| Flujo principal  | 1. El Administrador ingresa al módulo "Gestión de vehículos". El sistema despliega el listado general de vehículos registrados, el censo de celdas de parqueadero y opciones de búsqueda por placa, marca o apartamento.<br>2. El Administrador selecciona la acción a realizar: Gestión de Vehículos (Registrar, Editar, Borrar) o Gestión de Parqueaderos (Registrar, Editar, Eliminar parqueadero). El sistema presenta el formulario o panel correspondiente según la sub-opción elegida.<br>3. (Gestión de Vehículos) El Administrador ingresa la placa del vehículo. El sistema ejecuta la validación "Vehículo ya registrado" para comprobar si la placa ya se encuentra en el sistema.<br>4. El Administrador completa o modifica los datos del vehículo (Placa, Marca, Modelo, Color, Tipo: carro/moto, Residente/Apartamento asociado). El sistema valida el formato de la placa y la completitud de los datos obligatorios.<br>5. (Gestión de Parqueaderos) El Administrador vincula el vehículo a un espacio de estacionamiento (Registrar/Editar parqueadero). El sistema ejecuta la validación "Parqueadero ya registrado" para comprobar la existencia de la celda y que no esté asignada a otro vehículo activo.<br>6. El Administrador confirma y guarda la operación. El sistema almacena/actualiza la información del vehículo y la asignación del parqueadero en la base de datos, muestra un mensaje de confirmación y refresca el censo. |
| Flujos alternos  | **3A:** El Administrador intenta registrar una placa que ya existe en el sistema. El sistema notifica que el vehículo ya está registrado, mostrando los datos actuales e impidiendo la duplicación del registro.<br>**5A:** El Administrador intenta asignar un parqueadero que figura asignado a otro vehículo. El sistema emite una alerta indicando el conflicto de asignación e impide completar la operación hasta liberar la celda o elegir otro espacio.<br>**2B:** El Administrador solicita eliminar un registro de vehículo o desvincular un parqueadero. El sistema solicita confirmación mediante una ventana emergente. El Administrador confirma la desvinculación/eliminación. El sistema retira el registro de la base de datos, libera la plaza de parqueadero correspondiente y actualiza la lista en pantalla. |
| Postcondición    | El vehículo y/o su parqueadero asignado quedan guardados, actualizados o eliminados en la base de datos de C.A.M.P.U.S., regulando el control de acceso vehicular. |



### CU-07: Gestión de reportes
| Campo            | Descripción                                  |
|------------------|----------------------------------------------|
| Actor(es)        | Administración                               |
| Precondición     | El usuario debe haber iniciado sesión como Administración en la plataforma C.A.M.P.U.S y debe existir al menos un reporte de daños registrado por un residente (CU10) o por el personal de vigilancia/administración. |
| Flujo principal  | 1. El Administrador ingresa al módulo "Gestión de reportes". El sistema despliega el listado de reportes recibidos (Ver reportes subidos) clasificados por estado (Pendientes, En verificación, Aceptados, Rechazados).<br>2. El Administrador selecciona un reporte específico para inspeccionar (Verificar reportes). El sistema muestra los detalles del reporte: fecha, ubicación del daño, evidencia adjunta (imágenes/descripción) y datos del residente reportante.<br>3. El Administrador evalúa la veracidad de la incidencia e ingresa a la opción Rechazar-aceptar reportes. El sistema presenta las opciones para aprobar el trámite del reporte o desestimarlo, habilitando un campo para observaciones/justificación.<br>4. El Administrador marca el reporte como Aceptado para coordinar el mantenimiento/reparación y confirma. El sistema actualiza el estado a "Aceptado / En trámite", notifica la decisión al residente y guarda la trazabilidad en la base de datos.<br>5. El Administrador consulta la opción Ver reportes antiguos para revisar casos resueltos previamente. El sistema filtra y lista el historial de incidencias pasadas almacenadas en la plataforma. |
| Flujos alternos  | **3A:** El Administrador selecciona la opción "Rechazar reporte" por considerar la evidencia insuficiente o el reclamo infundado. El sistema solicita la causa o razón del rechazo.<br>El Administrador ingresa el motivo y confirma. El sistema cambia el estado del reporte a "Rechazado", almacena la observación y notifica la retroalimentación al residente.<br>**5A:** El Administrador solicita eliminar o depurar registros antiguos de la lista. El sistema emite una ventana de advertencia para confirmar la eliminación definitiva del historial.<br>El Administrador confirma la acción. El sistema elimina o inhabilita los registros seleccionados de la base de datos y refresca la vista. |
| Postcondición    | Permitir a la administración revisar, validar y darle seguimiento a los reportes de daños en la infraestructura o bienes del conjunto habitacional, identificar responsables y tomar acciones administrativas o sancionatorias. |


### CU-08: Gestion de bicicletas
| Campo            | Descripción                                  |
|------------------|----------------------------------------------|
| Actor(es)        | Administracion                               |
| Precondición     | El usuario de la administración debe haber iniciado sesión con credenciales válidas en la plataforma C.A.M.P.U.S. y deben existir residentes registrados en la base de datos. |
| Flujo principal  | 1. El Administrador ingresa al módulo "Gestión de bicicletas". El sistema despliega el inventario general de bicicletas registradas, con opción de búsqueda por serial/marco, color, residente o número de apartamento.<br>2. El Administrador selecciona la acción a realizar: Registrar bicicleta, Editar bicicleta o Borrar bicicleta. El sistema presenta el formulario o panel correspondiente según la sub-opción elegida.<br>3. (Registro) El Administrador ingresa el código de serial/marco o identificador único de la bicicleta. El sistema ejecuta la comprobación "Bicicleta ya registrada" para verificar que el serial no exista previamente en la base de datos.<br>4. El Administrador completa o modifica los datos del ciclo. El sistema valida que los campos obligatorios estén diligenciados correctamente.<br>5. El Administrador confirma y guarda los cambios. El sistema guarda/actualiza los datos en la base de datos, muestra un mensaje de éxito en pantalla y refresca el censo de bicicletas. |
| Flujos alternos  | **3A:** El Administrador intenta registrar un serial o marco que ya existe en el sistema. El sistema emite un aviso notificando que el vehículo ya está registrado, mostrando los datos del propietario actual e impidiendo el duplicado.<br>**2A:** El Administrador solicita eliminar el registro de una bicicleta del inventario. El sistema solicita confirmación de la acción mediante una ventana emergente de seguridad. El Administrador confirma la eliminación. El sistema retira el registro de la bicicleta de la base de datos, libera el espacio asignado en el biciparqueadero y actualiza la lista. |
| Postcondición    | La información de la bicicleta y su asignación de biciparqueadero quedan guardadas, modificadas o eliminadas en el sistema C.A.M.P.U.S., regulando el control de acceso y seguridad vehicular. |



### CU-09: Gestion de pagos
| Campo            | Descripción                                  |
|------------------|----------------------------------------------|
| Actor(es)        | Administracion                               |
| Precondición     | El usuario de la administración debe haber iniciado sesión con credenciales válidas en la plataforma C.A.M.P.U.S. y deben existir inmuebles (torres/apartamentos) parametrizados en el sistema. |
| Flujo principal  | 1. El Administrador ingresa al módulo "Gestión de pagos". El sistema despliega el listado general de inmuebles (Torre/Apartamento) sus estados de pago actuales y opciones de filtrado por estado (Al día, En mora) o periodo (mes/año).<br>2. El Administrador selecciona la acción a realizar: Ver información de pagos, Marcar pagos o Desmarcar pagos. El sistema presenta el panel con el detalle de cuentas o la lista de chequeo interactiva.<br>3. (Consulta) El Administrador selecciona la opción Ver información de pagos sobre un inmueble específico. El sistema muestra la ficha detallada de pagos: concepto (administración/sanción), fecha de cobro, historial de pagos y saldo pendiente.<br>4. (Registro de Pago) El Administrador selecciona la casilla/botón Marcar pagos para registrar el pago de un periodo correspondiente. El sistema solicita la confirmación de la transacción y permite adjuntar/digitar observaciones (ej. número de transferencia o fecha de consignación).<br>5. El Administrador confirma el registro del pago. El sistema actualiza el estado del inmueble a "Al día", guarda la fecha y hora de la marca en la base de datos, muestra confirmación en pantalla y actualiza la lista de chequeo. |
| Flujos alternos  | **4A:** El Administrador identifica un error en un pago marcado previamente y selecciona la opción Desmarcar pagos. El sistema emite una ventana de confirmación advirtiendo que el estado del inmueble cambiará nuevamente a "En mora / Pendiente".<br>El Administrador confirma la reversión del estado. El sistema desmarca el registro, recalcula el saldo pendiente del inmueble y actualiza la lista de chequeo. |
| Postcondición    | El estado de cuenta de los apartamentos queda actualizado (al día / mora) en la base de datos de C.A.M.P.U.S., reflejando la lista de chequeo de pagos. |


### CU-11: Reservas de zonas
| Campo            | Descripción                                  |
|------------------|----------------------------------------------|
| Actor(es)        | Residente                                    |
| Precondición     | El usuario debe haber iniciado sesión con rol de Residente en la plataforma C.A.M.P.U.S. y deben existir zonas comunes previamente parametrizadas y activas en el sistema por parte de la administración. |
| Flujo principal  | 1. El Residente ingresa al módulo "Reservas de zonas". El sistema despliega el catálogo de zonas comunes parametrizadas (fotos, aforo máximo, normas de uso, tarifas si aplican) y el calendario general de disponibilidad.<br>2. El Residente selecciona una zona común y consulta los horarios disponibles (Consultar zonas y horarios disponibles). El sistema muestra la agenda del área seleccionada indicando los bloques de tiempo libres y ocupados para la fecha elegida.<br>3. El Residente selecciona un horario disponible y presiona la opción para solicitar/aceptar la reserva. El sistema presenta el formulario de reserva solicitando detalles adicionales (tipo de evento, número de asistentes, comprobante de pago si la zona requiere tarifa).<br>4. El Residente diligencia el formulario, adjunta la información requerida y confirma el envío de la solicitud. El sistema valida que los campos estén completos, que el aforo no supere el límite permitido y que el horario no haya sido tomado previamente.<br>5. El Residente finaliza la solicitud. El sistema registra la reserva en estado "Pendiente", bloquea de forma temporal la casilla de tiempo en el calendario, envía un comprobante al residente y notifica a la administración para su verificación. |
| Flujos alternos  | **4A:** El Residente intenta confirmar una reserva en un rango de tiempo que acaba de ser ocupado por otro usuario. El sistema notifica que el horario ya no está disponible e invita al residente a seleccionar un nuevo bloque de tiempo o fecha.<br>**4B:** El Residente ingresa un número de invitados mayor a la capacidad configurada para la zona. El sistema muestra un mensaje de alerta indicando el límite de aforo permitido e impide el envío del formulario hasta ajustar la cantidad de personas. |
| Postcondición    | La solicitud de reserva queda registrada en el sistema en estado "Pendiente" y se notifica a la administración para su revisión y posterior aprobación o rechazo. |


### CU-12: Reportar daños
| Campo            | Descripción                                  |
|------------------|----------------------------------------------|
| Actor(es)        | Recidente                                    |
| Precondición     | El usuario de la administración debe haber iniciado sesión con credenciales de Administrador en la plataforma C.A.M.P.U.S. |
| Flujo principal  | 1. El Administrador ingresa al módulo "Publicar comunicados". El sistema despliega el historial de comunicados publicados y la opción para crear una nueva publicación.<br>2. El Administrador selecciona la opción "Crear nuevo comunicado". El sistema presenta el formulario de publicación (Título, Categoría, Alcance/Destinatarios, Cuerpo del mensaje y Adjuntos).<br>3. El Administrador completa la información del aviso, selecciona los destinatarios (Todo el conjunto o una torre específica) y adjunta documentos PDF/imágenes si aplica. El sistema valida que los campos obligatorios estén diligenciados y que los archivos no superen el tamaño máximo permitido.<br>4. El Administrador presiona el botón "Publicar". El sistema almacena la publicación en la base de datos, la hace visible en la cartelera digital de la plataforma y genera la notificación masiva para los residentes. |
| Flujos alternos  | **2A:** El Administrador selecciona una publicación existente y elige "Editar" o "Eliminar". El sistema habilita los campos para su modificación o solicita confirmación para retirar la publicación.<br>El Administrador confirma los cambios o la eliminación. El sistema actualiza los datos en pantalla o retira la noticia de la cartelera de los residentes.<br>**3A:** El Administrador intenta publicar sin título o con un archivo que supera el límite de tamaño. El sistema resalta los errores en pantalla e impide la publicación hasta que se corrjan los campos. |
| Postcondición    | El comunicado queda registrado y publicado en la cartelera digital de C.A.M.P.U.S., enviando una notificación general a los residentes seleccionados. |