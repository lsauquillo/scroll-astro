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
</template>