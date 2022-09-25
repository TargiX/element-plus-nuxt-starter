<script setup>
  import { ID_INJECTION_KEY } from 'element-plus'
  provide(ID_INJECTION_KEY, {
    prefix: 100,
    current: 0,
  })
  </script>

<template>
  <div class="container mx-auto px-4">
    <!-- Markup shared across all pages, ex: NavBar -->
    <NavBar />
    <NuxtPage />
  </div>
</template>