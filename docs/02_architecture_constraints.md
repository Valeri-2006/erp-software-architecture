# Restricciones de la Arquitectura

## Restricciones Técnicas

El desarrollo de SalonFlow ERP estará sujeto a las siguientes restricciones tecnológicas:

- El frontend utilizará React con TypeScript.
- El backend será desarrollado con C# utilizando ASP.NET Core (versión 8.0 o superior).
- La base de datos será PostgreSQL.
- El acceso a la base de datos se realizará mediante Entity Framework Core (EF Core).
- La autenticación se implementará mediante JWT (JSON Web Token) usando IdentityCore.
- Las contraseñas serán almacenadas utilizando Identity's built-in password hashing.
- La comunicación entre cliente y servidor será mediante API REST con HTTPS.

---

### Restricciones de Infraestructura
- **API Backend:** Azure App Service (free tier) o Render.com
- **Base de Datos:** Azure Database for PostgreSQL (free tier) o Railway
- **Frontend:** Vercel (gratis)
- **CI/CD:** GitHub Actions (gratis)

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
