<template>
  <div id="app">
  <div class="top" > <Card /></div>
    <Labels v-show="n" />
     <Buttos /> 
     <TingShu/>
    
  </div>
</template>

<script>

import Card from './components/体验卡.vue'
import Labels from './components/biaoqianye.vue'
import Buttos from './components/dibu.vue'
import TingShu from "./components/tingshu.vue"

export default {
  name: 'App',
  data() {
    return {
      i:2,
      n:false
    }
  },
  mounted() {
    this.$bus.$on("xxx", this.demo)
    if (this.i == 2) {
      this.n=true
    }
     
  },
  methods: {
    demo(value) {
   
      this.i = value
    
      switch (this.i) {
        case 1:
            this.n=false
          break;
          case 2:
          this.n = true
          break;
      case 3:
          this.n = false
          break;
        default:
          break;
      }
     
    }
  },
  components: { 
    Card,
    Labels,
    Buttos,
    TingShu
  }
}
</script>

<style scoped>
*{
  margin: 0;
  padding: 0;
}
.top{
 
  z-index: 2;
}

</style>
