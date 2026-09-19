# Diagrama del proceso actual

## Nombre Diagrama 

    A[Inicio: ...] --> B[Subproceso 1: ...]
    B --> C[Subproceso 2: ...]
    C --> D[Subproceso 3: ...]
    D --> E[Fin]
```

## Descripción de cada subproceso
- **[Subproceso 1]:** [qué ocurre, quién participa]
- **[Subproceso 2]:** [qué ocurre, quién participa]
- **[Subproceso 3]:** [qué ocurre, quién participa]


# Diagrama del proceso actual

## RESERVAS DE ZONAS DE EVENTO

    A[Inicio] --> B[Solicita reserva]
    B --> C[Muestra fechas y horas disponibles]
    C --> D[Verifica fecha y hora disponible en el sistema]
    D --> E[Envia reserva]
    E --> F[Guarda la reserva]
    F --> G[Verificar reserva]
    G --> H{¿Esta disponible?}
    H -- SI --> I[Enviar confirmacion al residente]
    H -- NO --> J[Enviar reporde de justificacion del administrador al residente]
    I --> K[Fin]
    J --> K[Fin]

## Descripción de cada subproceso
- **Solicita reserva:** El usuario inicia el trámite pidiendo una reserva. Participa: Residentes.
- **Muestra fechas y horas disponibles:** La plataforma devuelve y exhibe los horarios libres. Participa: Sistema.
- **Verifica fecha y hora disponible en el sistema:** El usuario revisa las opciones de tiempo que le entregó la plataforma. Participa: Residentes.
- **Envia reserva:** El usuario selecciona la fecha/hora deseada y manda la solicitud. Participa: Residentes.
- **Guarda la reserva:** La plataforma almacena los datos enviados en la base de datos. Participa: Sistema.
- **Verificar reserva:** El administrador revisa los detalles de la reserva que fue guardada. Participa: Administracion.
- **¿Esta disponible?:** Se toma la decisión sobre si aprobar o rechazar la solicitud basándose en la disponibilidad real. Participa: Administracion.
- **Enviar confirmacion al residente:** Si la decisión es "SI", se le notifica al usuario que su reserva fue un éxito. Participa: Sistema.
- **Enviar reporde de justificacion del administrador al residente:** Si la decisión es "NO", se le manda al usuario un mensaje explicando por qué se rechazó. Participa: Sistema.