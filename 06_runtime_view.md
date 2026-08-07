# Vista de Ejecución

## Escenario Crítico: Registrar un Producto

<img width="1123" height="398" alt="image" src="https://github.com/user-attachments/assets/ee7b9e8d-05c6-4ec0-a9c3-7e3d9a5693d2" />

![Diagrama de Secuencia](./images/sequence.png)

### Flujo de Interacción
1. El **Administrador** accede al módulo de inventario desde la aplicación web (React + TypeScript).
2. Completa el formulario con los datos del producto y hace clic en **Guardar**.
3. La **SPA** envía una solicitud `POST /api/productos` a la **API REST** (ASP.NET Core).
4. La **API** valida los datos recibidos y verifica la sesión activa mediante **Cookies + HttpContext**.
5. La **API** utiliza **Entity Framework Core** para insertar el producto en la base de datos PostgreSQL.
6. La **BD** confirma la creación del producto y devuelve el ID generado.
7. La **API** responde con un código `201 Created` y los datos del producto.
8. La **SPA** muestra un mensaje de éxito y actualiza la lista de inventario.

### Aspectos Notables
- Validación de campos obligatorios (nombre, stock inicial).
- Uso de **sesiones con cookies** para garantizar que solo usuarios autenticados puedan registrar productos.
- Persistencia mediante **EF Core** en PostgreSQL.
