<script setup>
const props = defineProps({
  title: String,
  color: String,
  imgSrc: String,
  level: Number,
});
</script>

<template>
  <v-card color="grey-darken-4" class="text-center pa-5" width="200">
    <v-img height="100" :src="props.imgSrc"> </v-img>

    <h1 class="text-h4 mb-4">{{ props.title }}</h1>
    <v-progress-circular
      :color="props.color"
      :model-value="props.level"
      size="100"
      width="10"
    >
      {{ props.level }}%
      <div>
        <h1><h2></h2></h1>
      </div>
    </v-progress-circular>
  </v-card>
</template>
