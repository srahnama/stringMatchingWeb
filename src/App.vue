<template>
  <div id="app">
    <About />
    <TableCustomSort :data="data" />
    <TableCustomSort :data="data1" />
    <TableCustomSort :data="data2" />
    <TableCustomSort :data="data3" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TableCustomSort from './components/TableCustomSort.vue'
import About from './components/About.vue'
import data from './assets/aesop11_result.json'
import data1 from './assets/gulliver_result.json'
import data2 from './assets/hitch2_result.json'
import data3 from './assets/hound-b_result.json'
export default {
  name: 'app',
  data: () => ({
      
      data:  data,    
      data1:  data1,    
      data2:  data2,    
      data3:  data3,    
    }),
  components: {
    TableCustomSort,
    About
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
