<style scoped>
* {
  margin: 0;
  padding: 0;
}
.hello{
  position: relative;
  width: 100%;
  min-height: 10vh;
 
  text-align: center;
}
input{
  width: 80vw;
  height: 30px;
  margin-top:10px ;
  border-radius:30px ;
  border: none;
  background: rgb(243, 242, 242);
  padding-left: 40px;
    border: none;
    outline: none;
}
.imgs{
  position: absolute;
  left: 4%;
  top:50%;
  width: 30px;
  height: 30px;

}
#esc-btn{
 position: absolute;
 left:3%;
}
</style>
<template>
    <div class="hello">
     <img src="../assets/img/尖括号-左.png" alt="" id="esc-btn" v-show="top" @click="escBtn" >
      <h3 >{{message}}</h3>
    
      <input type="text" placeholder="搜索" @focus="focusList" >
      <img src="../assets/img/搜索.png" alt="" class="imgs">
   
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
     return {
       message: '微信读书',
        top:false,
    }
  },
  methods: {
    //获得焦点
    focusList() {
      this.message = "搜索"
        this.top=true
    },
    //返回
    escBtn() {
      this.top = false
       this.message = "微信读书"
    }
  },
  watch: {
    top() {
       
      
    },
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

