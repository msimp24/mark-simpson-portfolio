<template>
  <v-main>
    <h1 class="text-h3 text-center mt-5">About Me</h1>
    <v-divider class="mt-5"> </v-divider>
    <v-container class="">
      <v-row class="algin-center">
        <v-col>
          <v-img
            cover
            width="300"
            class="rounded-circle"
            src="../assets/images/linked-in-profile.jpg"
          ></v-img>
        </v-col>
        <v-col>
          <v-sheet width="400" color="grey-darken-4" class="pa-5">
            <p><span class="text-orange">Name: </span>Mark Simpson</p>
            <p class="mt-5">
              <span class="text-orange">Phone: </span>506-651-1460
            </p>
            <p class="mt-5">
              <span class="text-orange">Email: </span>mark.simpson4@gmail.com
            </p>
            <p class="mt-5"><span class="text-orange">Country: </span>Canada</p>
            <p class="mt-5">
              <span class="text-orange">Education: </span>Bachelor of Computer
              Science from the University of New Brunswick (2016 - 2020)
            </p>
            <div class="text-center mt-5">
              <v-btn rounded variant="outlined" color="orange"
                >Download Resume</v-btn
              >
            </div>
          </v-sheet>
        </v-col>
      </v-row>
      <v-row>
        <v-col class="ma-6">
          <div>
            <p>My name is Mark Simpson</p>
            <br />
            <p>
              I am a freelance web developer and professional hockey player. I
              hold a bachelor's degree in Computer Science and have discovered a
              passion for software development. During my studies, I developed
              strong problem-solving and analytical skills that paved the way
              for my career in technology.
            </p>
            <br />
            <p>
              Alongside my academic pursuits, I've excelled in professional
              hockey, fostering teamwork, discipline, and the ability to perform
              under pressure. As a freelance web developer, I combine my
              technical expertise with a creative mindset. I have experience in
              front-end and back-end development, specializing in creating
              user-friendly interfaces and scalable solutions.
            </p>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<script setup></script>
