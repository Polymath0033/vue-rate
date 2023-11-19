<script setup lang="ts">
import { type Ref, ref } from 'vue';
const stars: Ref<string[]> = ref(Array(5).fill(''))

const clickHandler = (_: MouseEvent, star: number) => {
  //stars.value = stars.value.map((_, index) => index < star ? 'red' : '')
  
  console.log(star)
  for (let i = 0; i < stars.value.length; i++) {
    if (i < star) {
      stars.value[i] = 'red'
    }else{
      stars.value[i]=''
    }
  }
 

}
</script>

<template>
  <div>Vue App</div>
  <div class="flex text-white gap-3 pl-8">
    <button ref="btn" type="button" v-on:click="clickHandler($el, index)" v-for=" index in stars.length" :key="index"
      :class="`w-3 h-3 rounded-full bg-black flex justify-items-center justify-center items-center bg-${stars[index - 1]}-700  p-3 `"></button>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
