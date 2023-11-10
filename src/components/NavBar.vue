<script setup>
import { ref } from "vue";

const appTitle = ref("Mark Simpson");
const sidebar = ref(false);
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
  <v-app-bar app color="grey-darken-3">
    <v-toolbar-title> {{ appTitle }} </v-toolbar-title>
    <v-spacer></v-spacer>
    <v-app-bar-nav-icon
      variant="text"
      @click.stop="sidebar = !sidebar"
      class="hidden-md-and-up"
    ></v-app-bar-nav-icon>
    <v-toolbar-items
      class="hidden-sm-and-down"
      v-for="item in menuItems"
      :key="item"
    >
      <v-btn :key="`${item.value}-footer-link`" :to="item.value">{{
        item.title
      }}</v-btn>
    </v-toolbar-items>
    <div v-for="item in socialIcons" :key="item">
      <v-btn class="icons-hover" :icon="item.icon" :href="item.link"></v-btn>
    </div>
  </v-app-bar>

  <v-navigation-drawer
    color="grey-darken-3"
    v-model="sidebar"
    location="left"
    width="250"
    temporary
  >
    <v-list nav>
      <v-list-item
        v-for="link in menuItems"
        :key="link.title"
        :title="link.title"
        :prepend-icon="link.icon"
        :value="link.value"
        :to="link.value"
      >
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<style scoped>
.icons-hover:hover {
  transform: scale(1.1);
  cursor: pointer;
}
</style>
