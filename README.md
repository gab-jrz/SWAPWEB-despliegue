# SwapWeb: Nuestra aplicación web (MVP) de intercambios de producto en Argentina

SwapWeb
SwapWeb es una aplicación web desarrollada para facilitar el intercambio de productos entre usuarios, promoviendo el consumo responsable y la economía colaborativa. Se enfoca únicamente en el trueque (sin compras ni ventas), proporcionando una plataforma moderna, segura y eficiente.

Funcionalidades Principales

- Publicación de productos con título, descripción, imagen y categoría.
- Búsqueda avanzada y filtrado de productos.
- Propuesta de intercambios entre usuarios.
- Gestión de estados del intercambio: pendiente, aceptado, rechazado, completado.
- Sistema de mensajería interna entre usuarios.
- Gestión del perfil del usuario con imagen y configuración de privacidad.

🛠️ Tecnologías Utilizadas

Frontend

- React + Vite
- React Router DOM
- Bootstrap + CSS Modules
- Cypress (E2E testing)
- ESLint
- React Icons

Backend

- Node.js + Express
- MongoDB + Mongoose
- JWT para autenticación
- BcryptJS para seguridad
- Mocha, Chai, Sinon, Supertest (testing)
- Dotenv, Morgan, nodemon

Otros

JSON Server (mock API)
Jira (gestión de proyecto con Scrum)

📌 Arquitectura

- SwapWeb está construida sobre una arquitectura de 3 capas:
- Capa de Presentación (Frontend): interfaz de usuario en React.
- Capa de Lógica de Negocio (Backend): API REST en Express.
. Capa de Persistencia (Base de Datos): MongoDB con Mongoose.

🧪 Metodología de Trabajo

Se sigue el enfoque ágil Scrum, con:
- Sprints de desarrollo
- Reuniones diarias (daily)
- Planificación, revisión y retrospectivas por sprint
- Uso de Jira para historias de usuario y tareas

Sprints destacados:
Sprint 1: Setup del entorno y wireframes
Sprint 2: Registro/login y publicación de productos
Sprint 3: Intercambios y mensajería interna
Sprint 4: Testing, mejoras UI/UX y seguridad
Sprint 5: Refactorización, cobertura de tests y documentación final

🎯 Público Objetivo

+ *Usuarios interesados en el trueque como forma de consumo alternativo*
+ *Estudiantes y jóvenes que buscan renovar objetos sin gastar dinero*
+ *Familias y personas comprometidas con el consumo sostenible*
+ *Habitantes de ciudades grandes y medianas*

💡 Ventajas Competitivas

- Especialización en intercambios, no en ventas
- Seguridad, privacidad y autenticación robusta
- Interfaz moderna y amigable
- Fomento de comunidad mediante mensajería interna

---

## Despliegue

Este repositorio contiene Frontend (React + Vite) y Backend (Node.js + Express).

### Requisitos

- Node.js 18+
- MongoDB (local o remoto)

### Variables de entorno (Backend)

Crear `backend/.env` con, por ejemplo:

```
PORT=3001
MONGODB_URI=mongodb://localhost:27017/swapweb
JWT_SECRET=supersecreto
CLIENT_URL=http://localhost:5173
```

### Desarrollo local

- Frontend
  - `cd Frontend`
  - `npm install`
  - `npm run dev`

- Backend
  - `cd backend`
  - `npm install`
  - `npm run dev`

### Build de producción (Frontend)

```
cd Frontend
npm install
npm run build
npm run preview
```

El build se genera en `Frontend/dist/`.

### Notas de estilos del perfil

- Importar siempre `src/styles/profile-bundle.css` en `src/Pages/PerfilUsuario.jsx` para asegurar el orden y el scoping de estilos del perfil (todas las reglas están bajo `.perfil-usuario-container`).

### Despliegue sugerido

- Frontend: Netlify / Vercel (root `Frontend/`, comando `npm run build`, directorio `dist`).
- Backend: Render / Railway / Fly.io (root `backend/`, comando `npm start`).

### Archivos subidos en tiempo de ejecución

- El directorio `backend/uploads/` contiene archivos subidos por usuarios y fue agregado a `.gitignore`.
- Si ya fueron versionados, limpiarlos del índice manteniéndolos localmente:
  - `git rm -r --cached backend/uploads`
  - `git commit -m "chore: stop tracking backend/uploads"`
  - `git push`
