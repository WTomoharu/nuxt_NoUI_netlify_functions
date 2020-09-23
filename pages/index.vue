<template>
  <div class="container">
    <h2 v-text="'Netlify Functions × Nuxt.js サンプル'" />
    <p v-text="message" />
  </div>
</template>

<script>
import axios from 'axios'

export default {
  // data () {
  //   return {
  //     message: '---'
  //   }
  // }
  // asyncData () {
  //   const baseUrl =
  //     process.env.NODE_ENV !== 'production'
  //       ? 'http://localhost:9000'
  //       : process.env.URL
  //   return axios.get(baseUrl + '/.netlify/functions/hello').then((response) => {
  //     return {
  //       message: response.data
  //     }
  //   })
  // }
  asyncData () {
    return axios.get('http://.netlify/functions/hello').then((response) => {
      return {
        message: response.data
      }
    })
  }
}
</script>
