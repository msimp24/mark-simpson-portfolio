<script setup>
import NavBar from "./components/NavBar.vue";
import Footer from "./components/Footer.vue";
</script>

<template>
  <v-app class="bg-grey-darken-4">
    <NavBar />
    <router-view />
    <Footer />
  </v-app>
</template>
