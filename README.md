# Sistema de Gestión de Biblioteca

## Descripción del Proyecto
 API REST para gestionar una biblioteca digital con administración de libros, usuarios, préstamos, reservas, inventario multi-sucursal y reportes avanzados.

## Características Principales
- Gestión de libros, ejemplares y sucursales
- Préstamos y reservas con lógica de negocio avanzada
- Sistema de colas para reservas
- Gestión de multas y suspensiones
- Reportes y estadísticas para administración
- Autenticación y permisos por rol (JWT)

## Instalación y Ejecución
1. Clona el repositorio y entra al directorio del backend:
   ```bash
   git clone <repo_url>
   cd project/backend
   ```
2. Instala las dependencias:
   ```bash
   pip install -r requirements.txt
   ```
3. Configura la base de datos en `sistema_gestion_biblioteca/settings.py`.
4. Aplica migraciones:
   ```bash
   python manage.py migrate
   ```
5. (Opcional) Pobla la base de datos con datos de ejemplo:
   ```bash
   python manage.py populate_data
   ```
6. Ejecuta el servidor:
   ```bash
   python manage.py runserver
   ```

## Endpoints Principales
- **Autenticación:**
  - `POST /api/login/` (usuario y contraseña)
  - `POST /api/token/` y `/api/token/refresh/` (JWT)
- **Libros:**
  - `GET /api/libros/` (listado)
  - `GET /api/libros/buscar/` (búsqueda avanzada)
  - `GET /api/libros/{id}/` (detalle)
- **Préstamos y Reservas:**
  - `GET /api/prestamos/` (mis préstamos)
  - `POST /api/prestamos/` (crear préstamo)
  - `GET /api/usuarios/historial-prestamos/` (historial)
  - `GET /api/usuarios/mis-reservas/` (mis reservas)
- **Reportes:**
  - `GET /api/reportes/populares/` (libros más prestados)
  - `GET /api/reportes/morosidad/` (usuarios morosos)
  - `GET /api/reportes/estadisticas-sucursal/` (estadísticas por sucursal)

## Roles y Permisos
- **Usuario regular:** Buscar, reservar y solicitar préstamos.
- **Bibliotecario:** Gestiona préstamos, multas y transferencias.
- **Administrador:** Acceso completo al sistema.

## Autenticación
- JWT (djangorestframework-simplejwt)
- Incluye el token en el header: `Authorization: Bearer <token>`

## Créditos
- Autores: Jean Caripan, Carlos Silva
- Contactos: jean.caripan@inacapmail.cl, carlos.silva87@inacapmail.cl

---

