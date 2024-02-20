<script setup lang="ts">
import { ref } from 'vue'

defineProps<{ msg: string }>()

const count = ref(0)
const cardBackgroundColor = ref('');

const getRandomColor = () => {
      const letters = '0123456789ABCDEF';
      let color = '#';
      for (let i = 0; i < 6; i++) {
        color += letters[Math.floor(Math.random() * 16)];
      }
      return color;
    };


const doVV = () => {
  count.value++;
  cardBackgroundColor.value =getRandomColor();
}


</script>

<template>
  <h1>{{ msg }}</h1>

  <div  v-bind:style="{border: 1,backgroundColor: cardBackgroundColor}">
    <br><br><br><br><br>
    <button type="button" @click="doVV()">count is {{ count }}</button>
    <br><br><br><br><br>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
