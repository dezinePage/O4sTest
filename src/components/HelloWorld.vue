<script setup>
import { UAParser } from 'ua-parser-js'
defineProps({
  msg: {
    type: String,
    required: true
  }
})
const plat = window.navigator.platform
let OSName = 'Unknown OS'
let parser = new UAParser()
console.log(parser.getResult())
</script>

<template>
  <div class="greetings">
    <h3>Browser - {{ parser.getBrowser().name }}</h3>
    <h3>Browser Version - {{ parser.getBrowser().version }}</h3>
    <h3>OS - {{ parser.getOS().name }}</h3>
    <h3>OS Version - {{ parser.getOS().version }}</h3>
    <h3>Platform - {{ plat }}</h3>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
