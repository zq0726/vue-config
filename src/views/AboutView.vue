<template>
  <div class="about">
    <h1>This is an about page</h1>
    <main>{{ info }} -- {{ time }}</main>
  </div>
</template>

<script lang="ts" setup>
import { onMounted, ref } from 'vue'
const info = ref<string>('我想知道你在哪，你现在在干嘛')
const time = ref<string>('')

const changeTime = () => {
  setInterval(() => {
    time.value = new Date().getTime().toString()
  }, 1000)
}

onMounted(() => {
  changeTime()
})
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
  }
}

main {
  font-weight: bold;
  font-size: 30px;
  text-shadow: 0 5px 4px rgba(0, 0, 0, 0.5);
}
</style>
