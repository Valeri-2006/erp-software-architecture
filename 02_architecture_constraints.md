# Restricciones de la Arquitectura

## Restricciones Técnicas

El desarrollo de SalonFlow ERP estará sujeto a las siguientes restricciones tecnológicas:

- El sistema será desarrollado como una aplicación web responsive.
- El frontend utilizará React con TypeScript.
- El backend será desarrollado con Node.js y Express.
- La base de datos será PostgreSQL.
- El acceso a la base de datos se realizará mediante Prisma ORM.
- La autenticación se implementará mediante JSON Web Token (JWT).
- Las contraseñas serán almacenadas utilizando bcrypt.

---

## Restricciones de Infraestructura

- El sistema será desplegado utilizando plataformas cloud gratuitas para el proyecto académico.
- El frontend será desplegado en Vercel.
- El backend será desplegado en Railway.
- La base de datos PostgreSQL será alojada en Railway.

---

## Restricciones del Proyecto

- El proyecto será desarrollado durante un semestre académico.
- Se utilizará GitHub como sistema de control de versiones.
- Toda la documentación seguirá la plantilla arc42.
- La comunicación entre cliente y servidor se realizará mediante una API REST utilizando HTTPS y formato JSON.

---

## Restricciones de Negocio

- Solo los usuarios autenticados podrán acceder al sistema.
- Cada usuario tendrá permisos de acuerdo con su rol (Administrador, Recepcionista o Estilista).
- La información de clientes, inventario y ventas deberá mantenerse íntegra y disponible.
- El sistema deberá evitar la asignación de dos citas para el mismo estilista en el mismo horario.
