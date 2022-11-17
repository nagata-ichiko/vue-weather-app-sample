<template>
  <div class="wrapper">
    <div class="container">
      <Title />
      <Form @submit-form="getWeather" />
      <Results :results="results" />
  </div>
</div>
</template>
<script setup>
  import {reactive} from "vue"
  import axios from "axios"
  import Title from "./components/Title.vue"
  import Form from "./components/Form.vue"
  import Results from "./components/Results.vue";
  import "./assets/base.css"

  const getWeather = (city) => 
  {
    APIを使用　weatherapi.com
    axios.get(``)
        .then(res => 
        {
          results.contry = res.data.location.country,
          results.cityName = res.data.location.name,
          results.temperature = res.data.current.temp_c,
          results.conditionText = res.data.current.condition.text,
          results.icon = res.data.current.condition.icon
        })
  }

  const results = reactive({
    contry: "",
    cityName: "",
    temperature: "",
    conditionText: "",
    icon: ""
  })

</script>