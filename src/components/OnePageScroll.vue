<script setup>
const sections = [
  { id: "home", label: "Home" },
  { id: "pagina-1", label: "Página 1" },
  { id: "pagina-2", label: "Página 2" },
];

function goToSection(id) {
  document.getElementById(id)?.scrollIntoView({
    behavior: "smooth",
    block: "start",
  });
}
</script>

<template>
  <div class="min-h-screen bg-slate-950 text-white">
    <nav class="fixed top-0 left-0 z-50 w-full border-b border-white/10 bg-slate-950/80 backdrop-blur">
      <div class="mx-auto flex max-w-6xl items-center justify-between px-6 py-4">
        <span class="text-lg font-bold">Mi Web</span>

        <ul class="flex gap-6">
          <li v-for="section in sections" :key="section.id">
            <button
              class="text-sm font-medium text-slate-300 transition hover:text-white"
              @click="goToSection(section.id)"
            >
              {{ section.label }}
            </button>
          </li>
        </ul>
      </div>
    </nav>

    <main>
      <section
        id="home"
        class="flex min-h-screen items-center justify-center px-6 pt-20"
      >
        <div class="text-center">
          <h1 class="text-5xl font-bold">Home</h1>
          <p class="mt-4 text-slate-300">Primera pantalla de la landing.</p>
        </div>
      </section>

      <section
        id="pagina-1"
        class="flex min-h-screen items-center justify-center bg-slate-900 px-6 pt-20"
      >
        <div class="text-center">
          <h2 class="text-5xl font-bold">Página 1</h2>
          <p class="mt-4 text-slate-300">Contenido de la segunda sección.</p>
        </div>
      </section>

      <section
        id="pagina-2"
        class="flex min-h-screen items-center justify-center bg-slate-800 px-6 pt-20"
      >
        <div class="text-center">
          <h2 class="text-5xl font-bold">Página 2</h2>
          <p class="mt-4 text-slate-300">Contenido de la tercera sección.</p>
        </div>
      </section>
    </main>
  </div>
</template>