# Introducción y Metas

## Vista de Requerimientos

SalonFlow ERP es una aplicación web desarrollada para pequeñas peluquerías y barberías con el objetivo de centralizar la administración de los procesos operativos del negocio.

Actualmente, muchos establecimientos administran citas mediante WhatsApp, clientes en hojas de cálculo y el inventario de forma manual, lo que ocasiona pérdida de información, errores administrativos y poca trazabilidad.

SalonFlow ERP integra todos estos procesos dentro de una sola plataforma.

El sistema permitirá:

- Gestionar usuarios mediante roles.
- Administrar citas.
- Gestionar clientes.
- Registrar servicios realizados.
- Controlar el inventario.
- Calcular automáticamente las comisiones.
- Generar reportes administrativos.
- Visualizar indicadores mediante un Dashboard.

---

## Metas de Calidad

Las principales metas de calidad del sistema son:

### Usabilidad

El sistema debe ser intuitivo para usuarios con pocos conocimientos tecnológicos.

### Seguridad

Toda la información será protegida mediante autenticación con Session-based Authentication.

### Disponibilidad

El sistema deberá permanecer disponible durante el horario laboral del establecimiento.

### Rendimiento

Las consultas principales deberán responder en menos de tres segundos bajo condiciones normales.

### Escalabilidad

La arquitectura permitirá incorporar nuevos módulos como facturación electrónica o múltiples sucursales sin afectar los módulos existentes.

### Mantenibilidad

La arquitectura modular permitirá realizar modificaciones sin afectar el funcionamiento general del sistema.

---

## Partes Interesadas (Stakeholders)

| Rol | Contacto | Expectativas |
|------|----------|-------------|
| Administrador | Propietario del negocio | Gestionar completamente la peluquería y consultar indicadores. |
| Recepcionista | Personal administrativo | Registrar clientes y administrar las citas rápidamente. |
| Estilista | Empleado | Consultar agenda, registrar servicios y revisar sus comisiones. |
| Cliente | Usuario final | Recibir una atención organizada y acceder a un historial de servicios. |
| Equipo de Desarrollo | Grupo del proyecto | Construir una aplicación escalable, segura y mantenible. |
