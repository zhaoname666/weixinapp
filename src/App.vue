<template>
  <div id="app">
    <Card />
    <Labels />
     <Buttos /> 
  
    
  </div>
</template>

<script>

import Card from './components/体验卡.vue'
import Labels from './components/biaoqianye.vue'
import Buttos from './components/dibu.vue'

export default {
  name: 'App',
  components: { 
    Card,
    Labels,
    Buttos
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
}
</style>
