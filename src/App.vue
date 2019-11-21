<template>
  <div id="app">
    <ul>
      <li v-for="(ele, i) in data" :key="i">{{ele.name}}</li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'app',
  data () {
    return {
      data: []
    }
  },
  created() {
    axios.get('http://localhost:3000/api').then(res => {
      this.data = res.data
    }) 
  }
}
</script>

<style>
</style>
