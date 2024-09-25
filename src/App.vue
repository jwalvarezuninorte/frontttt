<script setup>
import axios from 'axios'
import { ref, onMounted } from 'vue'

const apiResponse = ref('');

async function getData() {
  axios.get('URL_HERE')
    .then(response => {
      apiResponse.value = response
    })
    .catch(error => {
      apiResponse.value = error;
      console.log(error)
    })
}

onMounted(() => {
  console.log('mounted')
  getData()
})


</script>

<template>
  <div>
    <h1>Hello World!</h1>
    {{ apiResponse }}
  </div>
</template>
