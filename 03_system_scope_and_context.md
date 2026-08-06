# Alcance y Contexto del Sistema

## Contexto de Negocio

SalonFlow ERP es una plataforma diseñada para centralizar la administración de pequeñas peluquerías y barberías.

El sistema permite gestionar usuarios, clientes, citas, servicios, inventario, comisiones y reportes desde una única aplicación web.

Los principales actores que interactúan con el sistema son:

- Administrador
- Recepcionista
- Estilista
- Cliente

Como sistemas externos se consideran:

- Servicio de correo electrónico para recuperación de contraseñas y notificaciones.
- WhatsApp Business (implementación futura) para el envío de recordatorios de citas.

### Diagrama de Contexto (C4 Nivel 1)

> **Inserte aquí el Diagrama C4 Nivel 1**

![Diagrama de Contexto](images/c1_context.png)

---

## Explicación del Contexto de Negocio

### Administrador

Gestiona completamente el funcionamiento de la peluquería, incluyendo usuarios, inventario, servicios, comisiones y reportes.

### Recepcionista

Registra clientes, administra la agenda y programa las citas.

### Estilista

Consulta su agenda, registra los servicios realizados y visualiza sus comisiones.

### Cliente

Solicita servicios y recibe atención por parte de la peluquería.

### Servicios Externos

El sistema podrá integrarse en el futuro con WhatsApp Business y correo electrónico para el envío de notificaciones.

---

# Contexto Técnico

SalonFlow ERP implementa una arquitectura cliente-servidor basada en una aplicación web.

El usuario accede mediante un navegador web, el cual consume una API REST desarrollada en Node.js y Express.

Toda la información es almacenada en una base de datos PostgreSQL utilizando Prisma ORM.

### Diagrama de Contenedores (C4 Nivel 2)

> **Inserte aquí el Diagrama C4 Nivel 2**

![Diagrama de Contenedores](images/c2_container.png)

---

## Explicación del Contexto Técnico

### Cliente Web

Aplicación desarrollada en React y TypeScript encargada de la interacción con los usuarios.

### API REST

Implementa toda la lógica de negocio del sistema.

Entre sus responsabilidades se encuentran:

- Autenticación
- Gestión de usuarios
- Gestión de clientes
- Agenda
- Inventario
- Servicios
- Comisiones
- Reportes

### Base de Datos

PostgreSQL almacena toda la información del sistema.

Entre las entidades principales se encuentran:

- Usuarios
- Roles
- Clientes
- Citas
- Servicios
- Productos
- Inventario
- Comisiones
- Ventas

---

## Mapeo de Entrada y Salida

| Entrada | Canal | Salida |
|----------|--------|---------|
| Inicio de sesión | Aplicación Web | Autenticación del usuario |
| Registro de clientes | Aplicación Web | Cliente almacenado |
| Registro de citas | Aplicación Web | Agenda actualizada |
| Registro de servicios | Aplicación Web | Venta registrada |
| Actualización de inventario | API REST | Stock actualizado |
| Consulta de reportes | Dashboard | Indicadores y estadísticas |
