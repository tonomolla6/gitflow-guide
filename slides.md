---
theme: default
background: https://images.unsplash.com/photo-1557683316-973673baf926?auto=format&fit=crop&w=1920
class: 'text-center'
highlighter: shiki
lineNumbers: false
info: |
  ## GitFlow
  Una guía completa sobre el flujo de trabajo GitFlow
drawings:
  persist: false
css: unocss
fonts:
  sans: 'Roboto'
  serif: 'Roboto Slab'
  mono: 'Fira Code'
---

# Dominando GitFlow
### Un vistazo rápido al flujo de trabajo más sólido de Git

<div class="abs-br m-6 flex gap-2">
  <a href="https://nvie.com/posts/a-successful-git-branching-model/" target="_blank" 
    class="text-xl opacity-50 !border-none !hover:text-white">
    <carbon-document-view />
  </a>
</div>

---
layout: intro
---

# ¿Por qué GitFlow? (y para quién)

<div class="grid grid-cols-2 gap-4 mt-4">
<div class="flex flex-col items-center">
  <div class="text-3xl mb-2">🎯</div>
  <h3>Organización</h3>
  <p class="text-sm opacity-75">Organización clara de ramas</p>
</div>
<div class="flex flex-col items-center">
  <div class="text-3xl mb-2">🤝</div>
  <h3>Colaboración</h3>
  <p class="text-sm opacity-75">Trabajo en equipo sin pisarnos</p>
</div>
<div class="flex flex-col items-center">
  <div class="text-3xl mb-2">🚀</div>
  <h3>Control</h3>
  <p class="text-sm opacity-75">Control estricto de releases y hotfixes</p>
</div>
<div class="flex flex-col items-center">
  <div class="text-3xl mb-2">👥</div>
  <h3>Ideal para</h3>
  <p class="text-sm opacity-75">Equipos medianos/grandes con releases periódicas</p>
</div>
</div>

---
layout: two-cols
---

# Estructura y Flujo

<div class="mt-4">
<div class="mb-6">
  <h3 class="text-blue-500">🔷 master</h3>
  <p class="ml-6 text-sm">Rama estable en producción</p>
</div>

<div class="mb-6">
  <h3 class="text-green-500">🔷 develop</h3>
  <p class="ml-6 text-sm">Integración de features</p>
</div>

<div class="mb-6">
  <h3 class="text-purple-500">🔷 feature/*</h3>
  <p class="ml-6 text-sm">Nuevas funcionalidades (a partir de develop)</p>
</div>
</div>

::right::

<div class="pl-4">
<div class="mb-6">
  <h3 class="text-yellow-500">🔷 release/*</h3>
  <p class="ml-6 text-sm">Preparar versión final (se fusiona en master + develop)</p>
</div>

<div class="mb-6">
  <h3 class="text-red-500">🔷 hotfix/*</h3>
  <p class="ml-6 text-sm">Parche urgente en producción (desde master)</p>
</div>
</div>

---
layout: center
---

# Flujo General

```mermaid {scale: 1.0}
gitGraph
   commit id: "1"
   branch develop
   commit id: "2"
   branch feature/login
   commit id: "3"
   commit id: "4"
   checkout develop
   merge feature/login
   branch release/1.0
   commit id: "5"
   checkout main
   merge release/1.0 tag: "v1.0"
   checkout develop
   merge release/1.0
   branch hotfix/1.0.1
   commit id: "6"
   checkout main
   merge hotfix/1.0.1 tag: "v1.0.1"
   checkout develop
   merge hotfix/1.0.1
```

---
layout: default
---

# Pros / Contras & Alternativas

<div class="grid grid-cols-3 gap-8 mt-8">

<div class="bg-green-50 p-6 rounded-lg">
  <h3 class="text-xl font-bold text-green-700 mb-4">✅ Pros</h3>
  <ul class="space-y-2 text-gray-700">
    <li>Estructura muy clara</li>
    <li>Facilita releases y hotfixes</li>
  </ul>
</div>

<div class="bg-red-50 p-6 rounded-lg">
  <h3 class="text-xl font-bold text-red-700 mb-4">❌ Contras</h3>
  <ul class="space-y-2 text-gray-700">
    <li>Excesivo en proyectos simples</li>
    <li>Más ramas = más merges</li>
  </ul>
</div>

<div class="bg-blue-50 p-6 rounded-lg">
  <h3 class="text-xl font-bold text-blue-700 mb-4">🔄 Alternativas</h3>
  <ul class="space-y-2 text-gray-700">
    <li>GitHub Flow: Más simple</li>
    <li>GitLab Flow: Más flexible</li>
  </ul>
</div>

</div>

---
layout: end
---

# Conclusión

<div class="text-xl text-gray-700 mt-4 space-y-4">
  <p>✨ GitFlow = orden y seguridad en el desarrollo</p>
  <p>🎯 Ideal para equipos con lanzamientos regulares</p>
  <p>⚠️ Evitar para proyectos muy pequeños</p>
</div>

<div class="mt-8">
  <a href="https://danielkummer.github.io/git-flow-cheatsheet/" target="_blank" class="text-blue-500">
    📚 GitFlow Cheatsheet
  </a>
</div>

<div class="text-2xl font-bold text-gray-800 mt-8">
  ¡Gracias!
</div>