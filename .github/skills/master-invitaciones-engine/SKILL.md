---
name: Master Invitaciones Engine
description: "Workflow skill for building and scaling interactive event invitation microsites with hero reveal, YouTube audio controls, RSVP handling, CSS variable theming, glassmorphism cards, and reusable event modules."
user-invocable: true
---

# Master Invitaciones Engine

Actúa como un Desarrollador Senior de Aplicaciones Web para Eventos. Este skill guía la creación de invitaciones interactivas para bodas, XV años, cumpleaños y celebraciones especiales usando una arquitectura clara y reusable.

## Objetivo

Producir micrositios de invitación con:
- Portada de apertura con `<section id="hero">` y botón `#btnOpen`.
- Contenido oculto inicialmente en `<main id="main-content">` que se revela al abrir.
- Reproductor de música basado en la YouTube IFrame API.
- Formulario RSVP que envía datos a Google Apps Script con `fetch(mode: 'no-cors')`.
- CSS theming mediante variables `:root` para facilitar cambios de piel.
- Layout responsivo basado en tarjetas, glassmorphism y paneles reutilizables.

## Paso a paso

1. Hero y apertura
   - Usar `#hero` como portada principal.
   - `#btnOpen` debe añadir `.hide` a `#hero` y quitar `.hidden` de `#main-content`.
   - Resetear scroll a `top: 0` cuando se abre la invitación.

2. Música
   - Implementar siempre la YouTube IFrame API con `YT.Player`.
   - Mantener estado booleano `isPlaying`.
   - Incluir botón flotante `.music-control` que controle `player.playVideo()` y `player.pauseVideo()`.
   - Cambiar icono y clase del botón según el estado.

3. RSVP y datos
   - Formularios deben enviar con `fetch` usando `mode: 'no-cors'`.
   - Enviar como `URLSearchParams` para compatibilidad con Google Apps Script.
   - Campos estándar: `name`, `message`, `attending`.
   - Manejar estados de envío y reset del formulario.

4. CSS y escalabilidad
   - Definir colores y estilos en `:root` como variables (`--primary`, `--bg-color`, `--text-color`, etc.).
   - No usar hex directos dentro de reglas de componentes; usar variables.
   - Usar glassmorphism para tarjetas y paneles.
   - Diseños basados en `display: grid` o `display: flex` y 100% responsivos.

5. Efectos de revelado
   - Usar `.scroll-reveal` en secciones modulares.
   - Activar `.active` con `IntersectionObserver` o `scroll`.
   - Garantizar animaciones suaves y progresivas en el contenido.

6. Módulos reutilizables
   - Crear componentes copy-paste friendly:
     - Itinerarios.
     - Galerías/carousels.
     - Mapas/ubicación.
     - Código de vestimenta.
     - Mensajes de cariño / regalos.
   - Mantener la misma lógica técnica y permitir cambiar la "piel" solo con variables CSS.

## Criterios de finalización

- `#hero` se oculta y `#main-content` se muestra con el botón de apertura.
- El reproductor de YouTube funciona con control de reproducción por botón.
- El formulario RSVP envía datos en formato `URLSearchParams` con `mode: 'no-cors'`.
- Los colores se gestionan desde `:root` y son fáciles de reemplazar.
- Las secciones se revelan con `.scroll-reveal` y `.active`.
- El diseño es responsive y usa tarjetas glassmorphism.

## Ejemplos de prompts

- "Crea una invitación de boda con `Master Invitaciones Engine` que incluya itinerario, galería y RSVP."
- "Genera un micrositio de XV años usando el flujo de hero + música + RSVP + diseño de variables CSS."
- "Diseña un módulo reusable de mapa y ubicación que pueda copiarse a otras invitaciones."
