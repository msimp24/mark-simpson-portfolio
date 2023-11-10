<script setup>
import { ref } from "vue";
import emailjs from "emailjs-com";

const form = ref(null);
const display = ref(true);

const user_email = ref("");
const user_name = ref("");
const message = ref("");
const formValidity = ref(false);

const contactItems = ref([
  {
    title: "Location",
    info: "Saint John, New Brunswick",
    icon: "mdi-map-marker",
  },
  {
    title: "Phone",
    info: "506-651-1460",
    icon: "mdi-phone",
  },
  {
    title: "Email",
    info: "mark.simpson4@gmail.com",
    icon: "mdi-send",
  },
]);

const nameRules = ref([(value) => !!value || "Please fill in a name"]);
const emailRules = ref([
  (value) => !!value || "Email is required",
  (value) =>
    value.match(
      /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
    ) || "Invalid Email address",
]);
const subjectRules = ref([(value) => !!value || "Please fill in a subject"]);
const textRules = ref([(value) => !!value || "Please add a message"]);

const sendEmail = () => {
  emailjs
    .send(
      "service_rsgzi4a",
      "template_9kmfk6v",
      {
        from_name: user_name.value + " (" + user_email.value + ")",
        reply_to: user_email.value,
        message: message.value,
      },
      "VfL-zyt-aHcdeq0Yf"
    )
    .then(
      () => {
        display.value = !display.value;
      },
      (error) => {
        alert("Message not sent", error);
      }
    );
};
</script>

<template>
  <v-main>
    <h1 class="text-h3 text-center mt-5">Contact Me</h1>
    <v-divider class="mt-5"> </v-divider>
    <v-container>
      <v-row class="align-center">
        <v-col lg="6" class="">
          <v-row class="flex-column justify-center align-center">
            <v-sheet
              width="200"
              class="bg-grey-darken-4 text-center ma-3 align-center"
              v-for="item in contactItems"
            >
              <v-icon color="orange" size="80">{{ item.icon }}</v-icon>
              <h3 class="text-center">{{ item.title }}</h3>
              <p class="text-center">{{ item.info }}</p>
            </v-sheet>
          </v-row>
        </v-col>
        <v-col class="align-center">
          <v-form
            ref="form"
            @submit.prevent="sendEmail()"
            :class="{ hide: !display }"
            v-model="formValidity"
          >
            <v-text-field
              label="Full Name"
              :rules="nameRules"
              v-model="user_name"
            >
            </v-text-field>
            <v-text-field
              label="Email"
              :rules="emailRules"
              v-model="user_email"
            >
            </v-text-field>
            <v-text-field label="Subject" :rules="subjectRules"> </v-text-field>
            <v-textarea v-model="message" label="Message" :rules="textRules">
            </v-textarea>
            <div class="text-center">
              <v-btn
                type="submit"
                width="200"
                rounded
                variant="outlined"
                color="orange"
                class="ma-5"
                :disabled="!formValidity"
                >Submit</v-btn
              >
            </div>
          </v-form>

          <div :class="{ hide: display }">
            <h1 class="text-h3 text-center">Thank you for your message!</h1>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<style scoped>
.hide {
  display: none;
}
</style>
