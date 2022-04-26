<script setup lang="ts">
import Input from './components/Input/Input.vue'
import { ref } from 'vue';
import type { Ref } from 'vue';

const name: Ref<string> = ref('')
const email: Ref<string> = ref('')
</script>

<template>
  <form action="">
    <Input v-model="name"/>
    <Input v-model="email" type="email" has-warning />
  </form>
  <p>User name: {{name}}</p>
  <p>User email: {{email}}</p>
</template>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: content-box;
}
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
}
</style>
