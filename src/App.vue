<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Menu from './components/Menu.vue';
</script>

<template>
  <Menu></Menu>
  <RouterView />
</template>

<style lang="scss">
:root {
  --background-color-2: #C599B6;
  --pastel-color-1: #E6B2BA;
  --pastel-color-2: #FAD0C4;
  --text-color: #fff7f3;

  --grey: #64748b;
  --dark: #1e293b;
  --dark-alt: #334155;
  --light: #f1f5f9;
  --sidebar-width: 300px;

  --dark-color: #1A1A1D;
  --dark-color-2: #1e1e1e;
  --background-color: #3B1C32;
  --main-color: #6A1E55;
  --pastel-color: #A64D79;
  --text-color: #fff7f3;
}

* {
  margin: 0;
  padding: 0;

  box-sizing: border-box;
  font-family: 'sansita', sans-serif;
}

body {
  color: var(--text-color);
  background: var(--dark-color-2);

  overflow-x: hidden;
}

#body {
  margin-left: calc(2rem + 32px) !important;
}

button {
  appearance: none;
  border: none;
  outline: none;
  background: none;

  cursor: pointer;
}
</style>