<script setup>
import { ref } from "vue";
import SkillCard from "../components/SkillCard.vue";

const skills = ref([
  {
    title: "HTML",
    color: "primary",
    level: 80,
    imgSrc: "src/assets/images/skills/html-logo.png",
  },
  {
    title: "Javascript",
    color: "green",
    level: 80,
    imgSrc: "src/assets/images/skills/javascript-logo.png",
  },
  {
    title: "CSS",
    color: "brown",
    level: 80,
    imgSrc: "src/assets/images/skills/css-logo.png",
  },
  {
    title: "Vue",
    color: "red",
    level: 80,
    imgSrc: "src/assets/images/skills/vue-logo.png",
  },
  {
    title: "SQL",
    color: "yellow",
    level: 80,
    imgSrc: "src/assets/images/skills/sql-logo.png",
  },
  {
    title: "Java",
    color: "indigo",
    level: 70,
    imgSrc: "src/assets/images/skills/java-logo.png",
  },

  {
    title: "Firebase",
    color: "orange",
    level: 70,
    imgSrc: "src/assets/images/skills/firebase-logo.png",
  },
  {
    title: "C",
    color: "light-green",
    level: 70,
    imgSrc: "src/assets/images/skills/c-logo.png",
  },
  {
    title: "Node JS",
    color: "purple",
    level: 60,
    imgSrc: "src/assets/images/skills/node-logo.png",
  },
  {
    title: "MongoDB",
    color: "teal",
    level: 50,
    imgSrc: "src/assets/images/skills/mongo-logo.png",
  },
]);
</script>

<template>
  <v-main>
    <h1 class="text-h3 text-center mt-5">Skills</h1>
    <v-divider class="mt-5"> </v-divider>

    <v-container class="">
      <v-row class="justify-center">
        <SkillCard
          v-for="item in skills"
          :key="item.title"
          :color="item.color"
          :level="item.level"
          :imgSrc="item.imgSrc"
          :title="item.title"
          class="ma-5"
        />
      </v-row>
    </v-container>
  </v-main>
</template>
