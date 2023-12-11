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

const expItems = ref([
  {
    year: "2023-present",
    title: "Freelance Web Developer",
    description:
      "Designed and developed an engaging landing page website that aligned with the clients brand identity and objectives.Successfully managed the project remotely,demonstrating strong communication,adaptability,and project management skills to meet deadlines",
    company: ["Entrepreneur"],
  },

  {
    year: "2020 - present",
    title: "Professional Hockey Player",
    description:
      "Pro hockey player currently playing for the Sheffield Steelers in the Elite Ice Hockey League in the UK. ",
    company: [
      "Sheffield Steelers, United Kingdom (2023-current)",
      "Asiago Hockey 1935 srl, Italy (2022-2023)",
      "Kalpa Kuopio, Finland (2022)",
      "Stockton Heat, United States (2020-2022)",
    ],
  },
  {
    year: "Summer 2017, 2018",
    title: "Database Administrator Intern",
    description:
      "Managed and maintained company databases,executed data retrieval and analysis,implemented robust security measures,and collaborated with the IT team to optimize databases.",
    company: ["JD Irving LTD."],
  },
]);
</script>

<template>
  <v-main>
    <h1 class="text-h4 ma-6 text-orange">Experience</h1>

    <v-container v-for="item in expItems" :key="item.title">
      <v-sheet
        class="bg-grey-darken-4 align-center d-flex flex-row justify-space-between pa-6 mt-5"
      >
        <v-row class="">
          <v-col cols="12" sm="4" class="d-flex justify-lg-center">
            <p class="text-h6">{{ item.year }}</p>
          </v-col>
          <v-col cols="12" sm="4">
            <div>
              <h1 class="text-h6">{{ item.title }} -</h1>
              <h1 class="text-h6" v-for="company in item.company">
                {{ company }}
              </h1>
            </div>
          </v-col>
          <v-col cols="12" sm="4" class="d-flex align-center">
            <p class="text-grey-lighten-2">
              {{ item.description }}
            </p>
          </v-col>
        </v-row>
      </v-sheet>
      <v-divider class="mt-5"> </v-divider>
    </v-container>

    <h1 class="text-h4 ma-6 text-orange">Skills</h1>

    <v-container class="">
      <v-row class="d-flex justify-center">
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

<style scoped></style>
