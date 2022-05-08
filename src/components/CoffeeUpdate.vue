<template>
  <div class="coffee">
    <h3>Input Yoisho Start</h3>
    <input v-model="time" placeholder="hh:mm:ss" />
    <p>Yoisho : {{ seconds }}</p>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const time = ref('')
const seconds = computed(() => {
  let arr = time.value.split(':')
  if (arr.length !== 3) {
    arr = ['00', ...arr]
  }
  const [hh, mm, ss] = arr.map((str: string) => parseInt(str))
  return hh * 60 * 60 + mm * 60 + ss
})
</script>

<style scoped>
h3 {
  margin: 10px;
}
</style>
