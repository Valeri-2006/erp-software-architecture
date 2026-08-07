# Vista de Bloques

## Sistema General de Caja Blanca

SalonFlow ERP está diseñado bajo una arquitectura por capas, donde cada módulo es responsable de una parte específica del negocio. Esta separación permite que el sistema sea escalable, mantenible y facilite la incorporación de nuevas funcionalidades sin afectar el resto de la aplicación.

### Diagrama General de Bloques

> **Inserte aquí el diagrama de componentes o de bloques**

![Vista de Bloques](images/building_blocks.png)

---

## Motivación

La arquitectura fue diseñada siguiendo el principio de separación de responsabilidades (Separation of Concerns), permitiendo que cada módulo se encargue de un proceso específico del negocio.

Cada bloque de construcción representa un conjunto de funcionalidades relacionadas entre sí, comunicándose mediante la API REST del sistema.

Esta organización facilita el mantenimiento del software, la reutilización del código y futuras ampliaciones del sistema.

---

# Bloques de Construcción Principales

## Capa de Presentación – Controladores API REST

**Responsabilidad:** Recibir solicitudes HTTP y coordinar las respuestas.

**Componentes:**
- `Controlador de Autenticación` → Inicio/cierre de sesión, registro de usuarios
- `Controlador de Citas` → Crear, editar, cancelar citas
- `Controlador de Clientes` → Registrar y gestionar clientes
- `Controlador de Inventario` → Controlar productos y stock
- `Controlador de Comisiones` → Consultar comisiones calculadas
- `Controlador de Reportes` → Generar reportes y dashboard

**Características:**
- Valida autenticación mediante sesión (cookie HTTP)
- Valida autorización según rol del usuario
- Delega lógica de negocio a los Servicios
- Retorna respuestas en formato JSON

---

## Capa de Aplicación – Servicios

**Responsabilidad:** Implementar la lógica de negocio y validaciones.

**Componentes:**
- `Servicio de Autenticación` → Gestiona login, logout y creación de sesión
- `Servicio de Citas` → Valida citas y evita conflictos de horario
- `Servicio de Clientes` → Gestiona datos e historial de clientes
- `Servicio de Inventario` → Descuenta stock y genera alertas
- `Servicio de Comisiones` → Calcula comisiones automáticamente (30%)
- `Servicio de Reportes` → Genera reportes consolidados

**Características:**
- Contienen las reglas de negocio del sistema
- No acceden directamente a la BD (usan Repositorios)
- Realizan validaciones antes de persistir datos
- Pueden usar otros servicios si es necesario

**Ejemplo:** `Servicio de Comisiones` calcula automáticamente: `Precio × 30% = Comisión`

---

## Capa de Datos – Repositorios

**Responsabilidad:** Abstraer el acceso a datos usando Entity Framework Core.

**Componentes:**
- `Repositorio de Usuarios` → Acceso a usuarios
- `Repositorio de Citas` → Acceso a citas
- `Repositorio de Clientes` → Acceso a clientes
- `Repositorio de Inventario` → Acceso a productos
- `Repositorio de Comisiones` → Acceso a comisiones

# Nivel 2

## Caja Blanca: Gestión de Usuarios

### Propósito

Administrar la autenticación de los usuarios y controlar los permisos de acceso al sistema.

### Responsabilidades

- Inicio de sesión.
- Recuperación de contraseña.
- Registro de usuarios.
- Edición de usuarios.
- Asignación de roles.

### Entradas

- Credenciales del usuario.
- Información del usuario.

### Salidas

- Token JWT.
- Información del usuario autenticado.

### Requerimientos que satisface

- Autenticación.
- Autorización.
- Seguridad.

---

## Caja Blanca: Gestión de Agenda

### Propósito

Administrar la programación de citas entre clientes y estilistas.

### Responsabilidades

- Registrar citas.
- Editar citas.
- Cancelar citas.
- Consultar disponibilidad.
- Confirmar atención.

### Entradas

- Información del cliente.
- Fecha.
- Hora.
- Estilista.

### Salidas

- Agenda actualizada.

### Requerimientos que satisface

- Organización de citas.
- Evitar conflictos de horario.

---

## Caja Blanca: Gestión de Clientes

### Propósito

Mantener la información de todos los clientes registrados.

### Responsabilidades

- Registrar clientes.
- Buscar clientes.
- Editar información.
- Consultar historial.
- Registrar preferencias.

### Entradas

- Datos personales.
- Información de contacto.

### Salidas

- Historial del cliente.

### Requerimientos que satisface

- Fidelización de clientes.
- Historial de servicios.

---

## Caja Blanca: Gestión de Servicios

### Propósito

Registrar todos los servicios realizados por los estilistas.

### Responsabilidades

- Registrar servicio.
- Asociar cliente.
- Asociar estilista.
- Registrar venta.

### Entradas

- Cliente.
- Servicio.
- Productos utilizados.

### Salidas

- Servicio registrado.
- Venta realizada.

### Requerimientos que satisface

- Historial de servicios.
- Registro de ventas.

---

## Caja Blanca: Gestión de Comisiones

### Propósito

Calcular automáticamente el valor correspondiente a cada estilista.

### Responsabilidades

- Configurar porcentaje.
- Calcular comisión.
- Generar liquidación.
- Consultar historial.

### Entradas

- Venta realizada.
- Configuración del estilista.

### Salidas

- Comisión calculada.

### Requerimientos que satisface

- Automatización de pagos.

---

## Caja Blanca: Gestión de Inventario

### Propósito

Controlar el inventario de productos utilizados durante los servicios.

### Responsabilidades

- Registrar productos.
- Registrar entradas.
- Descontar productos automáticamente.
- Generar alertas de bajo stock.
- Consultar movimientos.

### Entradas

- Productos.
- Cantidades.
- Servicios realizados.

### Salidas

- Inventario actualizado.

### Requerimientos que satisface

- Control de stock.
- Alertas automáticas.

---

## Caja Blanca: Reportes y Dashboard

### Propósito

Presentar información útil para apoyar la toma de decisiones.

### Responsabilidades

- Reportes diarios.
- Reportes mensuales.
- Ventas.
- Comisiones.
- Inventario.
- Dashboard.

### Entradas

- Información de todos los módulos.

### Salidas

- Reportes.
- Indicadores.
- Gráficos.

### Requerimientos que satisface

- Apoyo a la administración del negocio.

---

## Caja Blanca: Configuración

### Propósito

Administrar los parámetros generales del sistema.

### Responsabilidades

- Datos del negocio.
- Horarios.
- Métodos de pago.
- Configuración general.

### Entradas

- Parámetros del administrador.

### Salidas

- Configuración actualizada.

---

# Nivel 3

## Detalle interno del módulo Gestión de Inventario

El módulo de Inventario está compuesto por los siguientes componentes internos:

- Gestión de Productos
- Gestión de Entradas
- Gestión de Salidas
- Alertas de Stock
- Historial de Movimientos

Cada componente trabaja de forma integrada para mantener actualizado el inventario y garantizar que los productos utilizados durante los servicios sean descontados automáticamente.

---

## Detalle interno del módulo Gestión de Agenda

El módulo Agenda se divide en:

- Calendario
- Gestión de Citas
- Disponibilidad de Estilistas
- Confirmación de Atención

Estos componentes garantizan una correcta organización de la agenda y evitan conflictos entre las citas programadas.

---

## Detalle interno del módulo Reportes

Está conformado por:

- Reporte de Ventas
- Reporte de Inventario
- Reporte de Comisiones
- Dashboard Gerencial

Estos componentes permiten obtener información relevante para apoyar la toma de decisiones del administrador.
