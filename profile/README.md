<div align="center">

# 🎵 LetMCsound

### Marketplace de música para creadores

[![Frontend](https://img.shields.io/badge/Frontend-Vue%203-42b883?style=for-the-badge&logo=vue.js&logoColor=white)](https://github.com/LetMCsound/frontend)
[![Backend](https://img.shields.io/badge/Backend-Node%20%2B%20Express-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://github.com/LetMCsound/backend)
[![Database](https://img.shields.io/badge/Database-Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)](https://supabase.com)
[![Deploy](https://img.shields.io/badge/Deploy-Vercel%20%2B%20Render-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://vercel.com)

[🌐 Demo en vivo](https://letmcsound.vercel.app) · [📚 API Docs](https://letmcsound-backend.onrender.com/api-docs) · [📦 Frontend](https://github.com/LetMCsound/frontend) · [⚙️ Backend](https://github.com/LetMCsound/backend)

</div>

---

## 📖 Sobre el proyecto

**LetMCsound** es una plataforma web para creadores musicales donde productores, compositores, cineastas y diseñadores pueden **publicar, vender y descubrir contenido**: beats, letras, videos musicales y arte gráfico.

Los usuarios pueden:
- 🎵 Publicar y descubrir **beats, canciones y samples** con licencias Standard/Premium/Exclusiva
- ✍️ Compartir **letras** en varios idiomas
- 🎬 Mostrar **producciones audiovisuales** (videos musicales, behind-the-scenes, etc.)
- 🎨 Vender **diseños gráficos** (portadas, logos, branding)
- 💬 **Chatear** en tiempo real con otros artistas para negociar
- 💜 **Comentar y dar like** a contenido
- 📄 Descargar **contratos PDF** automáticos al comprar

---

## 🏗️ Arquitectura

```
┌─────────────────┐      ┌──────────────────┐      ┌──────────────────┐
│   Vue 3 + Vite  │ ───▶ │  Node + Express  │ ───▶ │     Supabase     │
│   (Frontend)    │ ◀─── │   (REST API)     │ ◀─── │  PostgreSQL +    │
│                 │      │                  │      │  Auth + Storage  │
└─────────────────┘      └──────────────────┘      └──────────────────┘
       Vercel                    Render                    SaaS
```

| Capa | Tecnología | Responsabilidad |
|------|------------|-----------------|
| **Frontend** | Vue 3, Vite, Pinia, Vue Router | UI/UX, gestión de estado, llamadas a la API |
| **Backend** | Node.js, Express, Joi, Swagger | REST API, validación, lógica de negocio, generación de PDFs |
| **Base de datos** | Supabase (PostgreSQL) | Persistencia con Row Level Security |
| **Auth** | Supabase Auth (JWT) | Registro, login, sesiones |
| **Storage** | Supabase Storage | Audios, portadas, vídeos |
| **Realtime** | Supabase Realtime | Chat y notificaciones en tiempo real |

---

## 📦 Repositorios

### [🎨 frontend](https://github.com/LetMCsound/frontend)
Aplicación Vue 3 con arquitectura modular por dominio. Desplegado en **Vercel**.

**Stack:** Vue 3, Vite, Pinia, Vue Router, Remix Icons

### [⚙️ backend](https://github.com/LetMCsound/backend)
REST API con arquitectura Controller → Service → Database. Desplegado en **Render**.

**Stack:** Node.js, Express, Joi (validación), Swagger/OpenAPI, pdf-lib (contratos PDF), Helmet + CORS + Rate Limiting

---

## ✨ Funcionalidades destacadas

| Funcionalidad | Tecnología |
|---------------|------------|
| Autenticación con JWT | Supabase Auth + middleware verificador |
| Subida de archivos | Supabase Storage con políticas RLS |
| Chat en tiempo real | Supabase Realtime (WebSockets) |
| Generación de contratos PDF | pdf-lib en Edge Function / Backend |
| Documentación interactiva | Swagger UI en `/api-docs` |
| Row Level Security | Políticas SQL en Supabase, JWT pasado al cliente |
| Light / Dark theme | CSS variables + composable `useTheme` |
| Búsqueda y filtros | PostgreSQL ilike + filtros client-side |

---

## 🚀 Cómo arrancar localmente

### Frontend
```bash
git clone https://github.com/LetMCsound/frontend.git
cd frontend
npm install
cp .env.example .env  # rellenar con tus credenciales de Supabase
npm run dev
```
Servidor en `http://localhost:5173`

### Backend
```bash
git clone https://github.com/LetMCsound/backend.git
cd backend
npm install
cp .env.example .env  # rellenar con tus credenciales
npm run dev
```
Servidor en `http://localhost:3000`
Docs en `http://localhost:3000/api-docs`

---

## 🎯 Gitflow

Ambos repos siguen el mismo flujo de ramas:

```
main          ← producción estable
 └── preproduccion    ← staging / QA
      └── desarrollo  ← desarrollo activo
           └── feature/*  ← ramas de feature
```

---

## 👤 Autor

**Martín** — Estudiante de Grado Superior

Proyecto desarrollado como entrega final de DAW.

---

<div align="center">

**Hecho con 💜 y mucho café**

</div>
