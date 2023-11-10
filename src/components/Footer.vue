<script setup>
import { ref } from "vue";

const menuItems = ref([
  {
    title: "Home",
    value: "/",
    icon: "mdi-home-outline",
  },
  {
    title: "About",
    value: "/about",
    icon: "mdi-information-outline",
  },
  {
    title: "Skills",
    value: "/skills",
    icon: "mdi-laptop",
  },
  {
    title: "Portfolio",
    value: "/portfolio",
    icon: "mdi-folder",
  },
  {
    title: "Contact",
    value: "/contact",
    icon: "mdi-phone-classic",
  },
]);

const socialIcons = ref([
  {
    icon: "mdi-linkedin",
    link: "https://www.linkedin.com/in/mark-simpson-230162145/",
  },

  {
    icon: "mdi-github",
    link: "https://github.com/msimp24",
  },
  {
    icon: "mdi-instagram",
    link: "https://www.instagram.com/msimp20/",
  },
]);
</script>

<template>
  <v-footer class="bg-grey-darken-3">
    <v-row class="flex-column" no-gutters>
      <v-toolbar-items class="pa-2" v-for="item in menuItems" :key="item">
        <v-btn
          class=""
          size="small"
          :key="`${item.value}-footer-link`"
          :to="item.value"
          >{{ item.title }}</v-btn
        >
      </v-toolbar-items>
      <div class="flex-row">
        <v-btn
          v-for="item in socialIcons"
          :key="item"
          :icon="item.icon"
          :href="item.link"
          class="bg-grey-darken-3 ma-2"
          size="x-small"
        ></v-btn>
      </div>
    </v-row>
    <v-col class="" cols="7">
      Created By: — <strong>Mark Simpson</strong>
      <br />
      <br />
      Last updated: {{ new Date().getFullYear() }}
    </v-col>
  </v-footer>
</template>
