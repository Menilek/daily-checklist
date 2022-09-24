<script setup lang="ts">
import { ref } from 'vue'

const healthyOptions = [
  "Have I eaten today?",
  "Have I taken a shower?",
  "Have I taken a walk outside for fresh air and sunlight?",
  "Have I gently challenged my negative self-talk?",
  "Have I engaged in some form of exercise?",
  "Have I decluttered a bit, organised an area, or otherwise improved my surroundings?",
  "Have I listed five things I'm grateful for?",
  "Have I meditated?",
  "Have I showed myself compassion?",
  "Have I validated my emotions?"
];

interface Option {
  text: string
}

// TODO: fix bug, occurred after avoiding type error
const selectedOptions = ref([""]);

const addToSelected = (option: string) => {
  selectedOptions.value.push(option);
};

</script>

<template>
  <w-app block>
    <main>
      <div>
        <w-flex v-for="option of healthyOptions" :key="option" class="align-center">
          <w-checkbox @change="addToSelected(option)">{{ option }}</w-checkbox>
        </w-flex>
      </div>
    </main>
  </w-app>
</template>

<style scoped>

</style>
