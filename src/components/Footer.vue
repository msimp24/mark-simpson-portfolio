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
    title: "Work",
    value: "/Work",
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
    <v-container>
      <v-row class="">
        <v-col
          ><v-toolbar-items class="pa-2" v-for="item in menuItems" :key="item">
            <v-btn
              class=""
              size="small"
              :key="`${item.value}-footer-link`"
              :to="item.value"
              >{{ item.title }}</v-btn
            >
          </v-toolbar-items>
        </v-col>
        <v-col class="mt-6">
          Created By: — <strong>Mark Simpson</strong>
          <br />
          <br />
          Last updated: {{ new Date().getFullYear() }}
        </v-col>

        <v-col>
          <div>
            <p class="">Phone: 506-651-1460</p>
            <p class="mt-2">Email: mark.simpson4@gmail.com</p>
            <p class="mt-2">Location: Saint John, NB, Canada</p>
          </div>

          <v-btn
            v-for="item in socialIcons"
            :key="item"
            :icon="item.icon"
            :href="item.link"
            class="bg-grey-darken-3 ma-2 mt-5"
            size="x-small"
          >
          </v-btn>
        </v-col>
      </v-row>
    </v-container>
  </v-footer>
</template>
