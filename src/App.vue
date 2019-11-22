<template>
  <div id="app">
    <div>🌶</div>
    <ul>
      
      <li v-for="(ele, i) in data" :key="i">{{ele.id}}--{{ele.name}}</li>
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
    axios.get('/api').then(res => {
      this.data = res.data
    }) 
  }
}
</script>

<style>
</style>
