<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <h2>{{ fromApi }}</h2>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  data () {
    return {
      fromApi: '読み込み中…'
    }
  },
  mounted () {
    const axios = require('axios')
    axios
      .get('/api/test')
      .then((response) => {
        this.fromApi = response.data.data
        console.log(response)
      })
  }
}
</script>
