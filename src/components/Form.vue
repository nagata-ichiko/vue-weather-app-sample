<template>
    <form @submit.prevent="submitForm">
        <input type="text" placeholder="都市名を英語で入力" v-model="city">
        <button type="submit">Get Weather</button>
    </form>
  </template>
  <script setup>
  import {ref} from "vue"

  const city = ref("")

  const submitForm = () => {
    emits("submit-form", city.value)
  }

  const emits = defineEmits([
    "submit-form"
  ])
  </script>
