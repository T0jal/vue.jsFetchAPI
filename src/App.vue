<template>
  <div id="app">
    <grid-section></grid-section>
  </div>
</template>

<script>
import GridSection from './components/GridSection.vue'

export default {
  name: 'App',
  components : {
    "grid-section" : GridSection
  },

  data: function(){
    return {
      mouseover : '',
    }
  },
  
  created(){
    window.Event.$on('mouseover', (data)=>{
      this.mouseover = data
    })
  }
}
</script>

<style>

body{
  background-color: #282C34;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #282C34;
}
</style>