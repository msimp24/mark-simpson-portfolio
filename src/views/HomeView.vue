<script setup>
import { ref } from "vue";

const services = ref([
  {
    title: "Website Development",
    icon: "mdi-laptop",
    text: "Develop visually appealing and user-friendly websites using HTML, CSS, JavaScript, Vue.js",
  },
  {
    title: "E-commerce Solutions",
    icon: "mdi-cart",
    text: "Creating online stores or integrating e-commerce functionalities into existing websites.",
  },
  {
    title: "Maintenance & Updates",
    icon: "mdi-wrench",
    text: "Providing ongoing support, updates, and maintenance services for websites.",
  },
]);
</script>

<template>
  <v-main class="ma-5">
    <v-container>
      <v-row class="align-center justify-center">
        <v-col>
          <h1 class="text-h3 font-weight-bold">Mark Simpson</h1>
          <h1 class="text-orange text-h6 mt-3 font-weight-bold">
            PRO HOCKEY PLAYER <span class="text-white">|</span><br />
            FREELANCE WEB DEVELOPER
          </h1>

          <v-btn href="/contact" color="orange" variant="outlined" class="mt-6"
            >Contact Me</v-btn
          >
        </v-col>
        <v-col>
          <v-img
            class="img-hover"
            src="../assets/images/prof-pic.png"
            width="580"
          />
        </v-col>
      </v-row>
    </v-container>

    <v-container class="mt-6">
      <h1 class="text-h3 text-center ma-6 text-orange">My Services</h1>
      <v-row class="justify-center">
        <v-col md="4" cols="8" v-for="item in services" :key="item">
          <v-card
            class="text-center"
            :icon="item.icon"
            :title="item.title"
            :subtitle="item.subtitle"
            :text="item.text"
            variant="outlined"
          >
            <v-icon class="ma-3" size="60">{{ item.icon }}</v-icon>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<style scoped>
.img-box {
  display: flex;
  align-items: center;
  justify-content: center;
}
.img-hover:hover {
  transform: scale(1);
}
</style>
