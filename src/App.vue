<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="m-5">
      <nav>
        <RouterLink
          to="/"
        >
          Home
        </RouterLink>
        <RouterLink
          to="/events"
          class="ml-4"
        >
          Events
        </RouterLink>
        <RouterLink
          to="/sign-up"
          class="ml-4"
        >
          Sign Up
        </RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>
