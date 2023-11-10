<script setup>
import { ref } from "vue";

const items = ref([
  {
    title: "Quiz App",
    info: " Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at.Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.",

    color: "orange",
    icon: "mdi-star",
    link: "https://opentrivia-quiz-app.onrender.com",
    techUsed: ["HTML", "Bulma CSS", "Javascript", "Vue JS"],
  },
  {
    title: "Tax Saver",
    info: " Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at.Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.",
    color: "black",
    icon: "mdi-book-variant",
  },
  {
    title: "Showboat",
    info: " Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at.Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.",
    color: "orange",
    icon: "mdi-airballoon",
  },
]);
</script>
<template>
  <v-main>
    <h1 class="text-h3 text-center mt-5">Portfolio</h1>
    <v-divider class="mt-5"> </v-divider>
    <v-container>
      <v-timeline align="start">
        <v-timeline-item
          v-for="(item, i) in items"
          :key="i"
          :dot-color="item.color"
          :icon="item.icon"
          fill-dot
        >
          <v-card>
            <v-card-title :class="['text-h6', `bg-${item.color}`]">
              {{ item.title }}
            </v-card-title>
            <v-card-text class="bg-white text--primary">
              <p>
                {{ item.info }}
              </p>
              <h1 class="ma-3 text-center">Technologies Used</h1>
              <v-list lines="">
                <v-list-item
                  v-for="list in item.techUsed"
                  :key="list"
                  :title="`- ` + list"
                  class="font-weight-bold"
                ></v-list-item>
              </v-list>

              <v-btn
                :href="item.link"
                class="mt-2"
                :color="item.color"
                variant="outlined"
              >
                View Website
              </v-btn>
            </v-card-text>
          </v-card>
        </v-timeline-item>
      </v-timeline>
    </v-container>
  </v-main>
</template>
