<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="bg-white shadow py-6">
      <nav>
        <router-link :to="{name:'home'}"/>Home</router-link>
      </nav>
    </div>
  </header>
  <div>
    <RouterView />
  </div>

  
</template>
