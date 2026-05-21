# TodoClean — Servicios del Hogar

![Privado](https://img.shields.io/badge/Codigo-Privado%20%C2%B7%20Proyecto%20Cliente-red?style=flat)
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nextjs/nextjs-original.svg" width="18" align="absmiddle" /> ![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat&logo=nextdotjs&logoColor=white)
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/react/react-original.svg" width="18" align="absmiddle" /> ![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/typescript/typescript-original.svg" width="18" align="absmiddle" /> ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-06B6D4?style=flat&logo=tailwindcss&logoColor=white)
![PWA](https://img.shields.io/badge/PWA-5A0FC8?style=flat&logo=pwa&logoColor=white)

> **Plataforma PWA que conecta duenos de hogares con profesionales verificados — reservas de limpieza, jardineria, plomeria y mas en minutos, sin necesidad de cuenta.**

> Este es un **portfolio showcase** — el codigo fuente es propietario y no esta incluido.

---

## El Sitio

**[todocleanservicios.sytes.net](https://todocleanservicios.sytes.net/)** — sitio en produccion.

---

## El Problema

Contratar servicios del hogar es un proceso fragmentado: busquedas en redes sociales, llamadas sin respuesta, proveedores sin verificacion y sin historial visible. Los clientes no saben con quien contratan, y los contratistas independientes no tienen canal para conseguir clientes de forma constante.

---

## La Solucion

TodoClean es un marketplace bidireccional donde los clientes reservan en minutos (sin crear cuenta), los contratistas reciben asignaciones directas, y el admin gestiona toda la operacion desde un dashboard centralizado.

---

## Funcionalidades

| Funcionalidad | Descripcion |
|--------------|-------------|
| Reserva sin cuenta | Los clientes envian solicitudes con nombre, telefono, direccion, servicio y fecha |
| Dashboard admin | Vista de todas las reservas — pendientes, asignadas y completadas |
| Asignacion de trabajos | El admin asigna contratistas disponibles a cada reserva |
| Panel del contratista | Los profesionales ven sus trabajos asignados al iniciar sesion |
| PWA instalable | Funciona como app nativa en Android e iOS — con pagina offline personalizada |
| Roles diferenciados | Flujos separados para cliente / contratista / admin desde una sola aplicacion |

---

## Arquitectura

```mermaid
graph TD
    GUEST["Cliente sin cuenta"]
    CONTRACTOR["Contratista"]
    ADMIN["Administrador"]

    subgraph APP ["TodoClean — Next.js 16 App Router"]
        BOOK["Formulario de Reserva"]
        CONDASH["Dashboard Contratista"]
        ADASH["Dashboard Admin"]
        API["Route Handlers REST"]
        DATA["JSON Store en servidor\nbookings.json / workers.json"]
        SW["Service Worker\nSoporte offline + PWA"]
    end

    GUEST --> BOOK
    CONTRACTOR --> CONDASH
    ADMIN --> ADASH
    BOOK --> API
    CONDASH --> API
    ADASH --> API
    API --> DATA
```

---

## Stack Tecnologico

| Capa | Tecnologia |
|------|-----------|
| Framework | Next.js 16 (App Router, Turbopack) |
| UI | React 19 · Tailwind CSS 4 |
| Lenguaje | TypeScript 5 |
| API | Next.js Route Handlers (REST) |
| Persistencia | JSON file store via Node.js `fs` |
| PWA | Web App Manifest + Service Worker personalizado |
| Despliegue | Linux VPS · PM2 · Bluehost |

---

## Vista Previa

<img src="assets/preview.jpeg" width="100%" alt="TodoClean — Conectamos Hogares con Profesionales" />

---

## Contacto

El codigo fuente es propietario. Para consultas: [pablozam1931@gmail.com](mailto:pablozam1931@gmail.com)

---

*Parte del portfolio [deadlyrat](https://github.com/deadlyrat).*
