---
marp: true
theme: default
paginate: true
style: |
  h1 {color: white}
  .lead {color: white}
  section {
    background:rgb(58, 58, 58);
    color: white;
  }
  blockquote {
    color: white;
    border-left: 5px solid white;
  }
class: lead
---

# 🛠️ React DevTools

---

## 🎯 Contenido

1. 🌟 Introducción a React DevTools
2. 📥 Instalación
3. 🔍 Components Panel
4. 📊 Profiler Panel
5. ⚙️ Configuración y Tips

---

## 🌟 1. Introducción a React DevTools

React Developer Tools es una herramienta oficial mantenida por el equipo de React. Su propósito es inspeccionar, depurar y optimizar aplicaciones React directamente desde el navegador.

React Developer Tools es **obligatorio** para cualquier developer de React. Si no lo estás usando, básicamente estás programando a ciegas con respecto a la estructura de componentes, el flujo de estado y el rendimiento.

---

## 📥 2. Instalación

Instala el [complemento de Chrome](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi) y cuando uses una página con React aparecerán las pestañas **Components** y **Profilers** (Cierra y vuelve a abrir el navegador en el caso de que no aparezca).

Páginas para probar: https://react.dev y https://www.airbnb.com/

> ¿Has instalado el complemento? ¿Has verificado que funciona en alguna página con React? (El profiler funciona en modo dev)

---

## 🔍 3. Components Panel

**Funcionalidades principales:**

- 🌳 Ver la jerarquía completa de componentes React (no solo nodos DOM)
- ✏️ Editar state y props en vivo (debugging, no se persisten)
- 🎯 Identificar instantáneamente componentes container vs presentacionales:
  - **Hooks section** → 🧠 Container
  - **Solo Props, sin hooks** → 🎨 Presentacional

> ¿Has inspeccionado la estructura de componentes de alguna app React? ¿Has editado props o state en vivo? ¿Puedes distinguir componentes container de presentacionales?

---

<img src="https://jorgebenitezlopez.com/tiddlywiki/pro/icomponents.jpg">

---

## 📊 4. Profiler Panel

> ⚠️ **Importante**: Tiene que estar en modo dev para que funcione. Probar en local en modo dev.

Puedes grabar el comportamiento y ver sus renderizados. Grabas y recargas desde el profiler.

**Análisis disponible:**

- 📈 **Gráfico de carga**: Visualización temporal de renders
- 🏆 **Ranking de tiempo**:  Durations

> ¿Has usado el Profiler en modo dev? ¿Has grabado una sesión y analizado los tiempos de renderizado?

---

<img src="https://jorgebenitezlopez.com/tiddlywiki/pro/profilers.jpg">

---

**Métricas clave del Profiler:**

- ⏱️ **Render time**: Tiempo en renderizarse. Te ayuda a identificar componentes lentos que necesitan optimización (memo, useMemo, etc.). Render no cambia la pantalla: solo es cálculo.

- 🔄 **Commit**: Cada "commit" representa una actualización completa de la UI. React agrupa todos los cambios  (Renders) en un solo commit para actualizar el DOM de forma eficiente. Puedes ver cuántos commits ocurren durante una interacción. Render es barato commit es caro

- 🎭 **Passive effects**: Efectos que se ejecutan después del renderizado (como `useEffect`). Se ejecutan en el orden: Render → Commit → Paint → Passive Effects. Útil para identificar efectos costosos que pueden estar bloqueando la UI.

---

## ⚙️ 5. Configuración y Tips

**Highlight component updates**: En ⚙️ Settings. Check: ☑ Highlight updates when components render

Esta opción resalta visualmente qué componentes se están renderizando en tiempo real, lo cual es muy útil para identificar renders innecesarios.

> ¿Has activado el highlight de actualizaciones? ¿Has identificado componentes que se renderizan más de lo necesario?

---

<!-- _class: lead -->
## 🎉 ¡Gracias!

Lo que no se evalúa se devalúa

Lo que se mide, se puede mejorar

Acostúmbrate a auditarte 😉
