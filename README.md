<div align="center">

# AssetTrack
### Control de Préstamos y Activos de Valor

![Version](https://img.shields.io/badge/version-1.0.0-blue?style=for-the-badge)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-black?style=for-the-badge&logo=JSON%20web%20tokens)

Plataforma de inventario dinámico para el control, préstamo y trazabilidad de activos de valor en organizaciones.

</div>

---

## Tabla de Contenidos

- [Descripción](#descripción)
- [Problema](#problema)
- [Solución](#solución)
- [Funcionalidades](#funcionalidades)
- [Requisitos Funcionales](#requisitos-funcionales)
- [Requisitos No Funcionales](#requisitos-no-funcionales)
- [Equipo](#equipo)

---

## Descripción

**AssetTrack** es una plataforma web full stack diseñada para que organizaciones gestionen de forma rigurosa el ciclo de vida completo de sus activos de valor: desde el registro del equipo, pasando por solicitudes de préstamo, hasta la devolución con evidencia fotográfica del estado. Elimina el caos del papel y los chats informales, reemplazándolos por un sistema centralizado, trazable y con notificaciones automáticas.

---

## Problema

En muchas organizaciones, el equipo costoso —cámaras, drones, herramientas especializadas, portátiles o kits de laboratorio— se presta de mano en mano **sin un registro digital riguroso**, lo que genera:

- Pérdida de equipos sin responsable identificado
- Daños sin saber quién fue el último custodio
- Bloqueos operativos porque nadie sabe quién tiene el activo en un momento dado
- Ausencia de historial para auditorías o reclamaciones

---

## Solución

AssetTrack ofrece un **inventario dinámico** donde cada activo tiene una hoja de vida completa. Los usuarios pueden consultar disponibilidad en tiempo real, solicitar préstamos por periodos definidos, recibir alertas automáticas de devolución, reportar el estado del equipo con fotos de evidencia al entregarlo y consultar el historial completo de custodios.

---

## Funcionalidades

| Módulo | Descripción |
|--------|-------------|
| **Autenticación** | Login seguro con JWT, manejo de roles (Admin / Usuario) |
| **Gestión de Activos** | CRUD completo: registro, fotos, manuales, estado actual |
| **Solicitudes de Préstamo** | Flujo de solicitud, aprobación, entrega y devolución |
| **Alertas de Devolución** | Notificaciones automáticas antes y después del vencimiento |
| **Historial de Custodios** | Trazabilidad completa de quién tuvo cada activo y cuándo |
| **Reporte de Estado** | Registro fotográfico del estado del equipo al momento de la devolución |
| **Panel de Administrador** | Gestión de usuarios, activos, solicitudes y reportes globales |

---

## Requisitos Funcionales

### RF-01 · Autenticación y Roles
- **RF-01.1** El sistema debe permitir el registro e inicio de sesión de usuarios con correo y contraseña.
- **RF-01.2** El sistema debe diferenciar dos roles: `ADMIN` y `USUARIO`.
- **RF-01.3** El acceso a rutas protegidas debe requerir un token JWT válido.
- **RF-01.4** El administrador puede crear, editar y desactivar cuentas de usuario.

### RF-02 · Gestión de Activos
- **RF-02.1** El administrador puede registrar activos con nombre, descripción, categoría, fotos y manuales.
- **RF-02.2** Cada activo debe tener un estado: `DISPONIBLE`, `PRESTADO`, `EN MANTENIMIENTO` o `DADO DE BAJA`.
- **RF-02.3** El sistema debe permitir actualizar el estado y la información de un activo.
- **RF-02.4** Los usuarios pueden consultar el inventario y filtrar por estado o categoría.

### RF-03 · Solicitudes de Préstamo
- **RF-03.1** Un usuario puede solicitar el préstamo de un activo disponible indicando fechas de inicio y devolución.
- **RF-03.2** El administrador puede aprobar o rechazar la solicitud.
- **RF-03.3** Al aprobar, el sistema cambia el estado del activo a `PRESTADO` automáticamente.
- **RF-03.4** Al devolver, el usuario debe registrar el estado del equipo y puede adjuntar fotos de evidencia.

### RF-04 · Alertas y Notificaciones
- **RF-04.1** El sistema debe enviar una notificación al usuario 24 horas antes de la fecha de devolución.
- **RF-04.2** Si el activo no es devuelto en la fecha pactada, el sistema debe alertar al administrador.
- **RF-04.3** El usuario debe recibir confirmación cuando su solicitud sea aprobada o rechazada.

### RF-05 · Historial de Custodios
- **RF-05.1** El sistema debe registrar automáticamente cada cambio de custodio de un activo.
- **RF-05.2** El historial debe incluir: usuario, fechas de préstamo/devolución y estado reportado.
- **RF-05.3** El administrador puede consultar el historial completo de cualquier activo.

### RF-06 · Panel de Administrador
- **RF-06.1** El administrador puede ver un dashboard con resumen de activos por estado.
- **RF-06.2** El administrador puede generar reportes de activos prestados, devueltos y con incidencias.

---

## Requisitos No Funcionales

### RNF-01 · Seguridad
- **RNF-01.1** Las contraseñas deben almacenarse con hash `BCrypt`.
- **RNF-01.2** La autenticación debe usar tokens JWT con expiración configurable.
- **RNF-01.3** Las rutas de administrador deben estar protegidas por verificación de rol en el backend.

### RNF-02 · Rendimiento
- **RNF-02.1** El tiempo de respuesta de la API no debe superar **2 segundos** para consultas estándar.
- **RNF-02.2** El sistema debe soportar al menos **100 usuarios concurrentes** sin degradación notable.

### RNF-03 · Usabilidad
- **RNF-03.1** Las acciones críticas (eliminar, rechazar) deben solicitar confirmación al usuario.
- **RNF-03.2** Los mensajes de error deben ser claros y en español.

### RNF-04 · Disponibilidad
- **RNF-04.1** El sistema debe tener una disponibilidad mínima del **99%** en horario laboral.

### RNF-05 · Escalabilidad
- **RNF-05.1** La arquitectura debe permitir agregar nuevos módulos (ej: QR por activo) sin refactorizar el core.

---

## Equipo

<table>
  <tr>
    <td align="center">
      <b>Diego Alejandro Villegas Velasquez</b><br/>
      <sub>Full Stack Developer</sub>
    </td>
    <td align="center">
      <b>Maria del Pilar Mantilla Gelves</b><br/>
      <sub>Full Stack Developer</sub>
    </td>
    <td align="center">
      <b>Maria Fernanda Muñoz Acosta</b><br/>
      <sub>Full Stack Developer</sub>
    </td>
  </tr>
</table>
