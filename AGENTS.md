# 📂 AGENTS.md - Pokedex Next.js Senior Architecture

## 🎯 Visión del Proyecto
Construcción de una Pokedex de grado producción utilizando **Next.js 15+**. El enfoque principal es la **excelencia técnica**, priorizando el rendimiento (Core Web Vitals), la escalabilidad de la arquitectura y un sistema de tipos inquebrantable.

---

## 🛠 Stack & Patterns (Senior Level)
*   **Framework:** Next.js 15 (App Router) con React 19.
*   **Data Fetching:** Server Components (RSC) por defecto. Uso de `fetch` nativo con caché extendida.
*   **Validación:** `Zod` para validación de contratos de API en tiempo de ejecución.
*   **Estilos:** Tailwind CSS (Arquitectura de diseño atómico).
*   **Componentes:** Shadcn/UI + Radix UI para accesibilidad (WAI-ARIA).
*   **Tipado:** TypeScript estricto (no `any`).

---

## 🏛 Principios de Ingeniería

### 1. Data Access Layer (DAL)
*   Centralización de PokeAPI en `@/lib/api` o `@/services`.
*   Validación de esquemas con **Zod** obligatoria.

### 2. Rendimiento y Caching
*   **ISR/SSG:** Uso de `generateStaticParams`.
*   **Streaming UI:** Uso intensivo de `loading.tsx` y `Suspense`.
*   **Image Optimization:** Uso estricto de `next/image` para evitar CLS.

### 3. URL-Driven State
*   Búsqueda y filtros gestionados mediante `searchParams` para persistencia y SEO.

---

## 📝 Protocolo de Documentación y Control
Como asistente de IA, debo cumplir estrictamente con los siguientes pasos en cada intervención que implique cambios en el código:

### 1. Documentación Técnica (`/docs`)
Toda nueva funcionalidad, cambio arquitectónico o decisión de diseño debe quedar registrada en la carpeta `/docs` en archivos Markdown. 
*   Ejemplo: `/docs/data-fetching-strategy.md`, `/docs/component-library.md`.

### 2. Versionado (`package.json`)
Cualquier modificación de lógica o estructura requiere incrementar la versión en el `package.json` siguiendo **Semantic Versioning (SemVer)**:
*   `MAJOR.MINOR.PATCH` (Rompe compatibilidad / Nueva funcionalidad / Correcciones).

### 3. Registro de Cambios (`CHANGELOG.md`)
Cada modificación debe reflejarse en el archivo `CHANGELOG.md` siguiendo estrictamente el formato de [Keep a Changelog](https://keepachangelog.com/es-ES/1.0.0/):
*   Secciones: `Añadido`, `Modificado`, `Depreciado`, `Eliminado`, `Corregido`, `Seguridad`.

---

## 🤖 Instrucciones para el Asistente IA
1.  **Rol Tech Lead:** Explica el "porqué" arquitectónico antes del código.
2.  **Next.js 15 Ready:** Uso de `params` y `searchParams` como promesas (asíncronos).
3.  **Refactorización Proactiva:** Sugerir Custom Hooks o Server Actions si la complejidad crece.
4.  **Flujo Obligatorio:** Antes de finalizar una tarea, generar/actualizar la documentación en `/docs`, actualizar `package.json` y redactar la entrada en `CHANGELOG.md`.