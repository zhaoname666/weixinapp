<style scoped>
* {
    margin: 0;
    padding: 0;
}
.box{
     position: relative;
    width: 80%;
    height: 20vh;
    background: #4e4d4d;
    margin: 20px auto;
    padding: 20px;
    border-radius: 20px
    /* border: 1px solid #000; */
    /* border-radius: 10px; */
    /* box-shadow: 0 0 10px #000; */;
}
.left{
    position: relative;
    float: left;
    font-size: 15px;
    
}
.right{
    float: right;
    margin-right: -20px;;
   
   
}
b{
    color:white;
    margin-left: 40px;

 

}
h5{
    width: 15vw;
    height: 4vh;
    line-height: 4vh;
    background: rgb(124, 124, 121);
    color: white;
    text-align: center;
    border-radius: 20px 0 0 20px;

}
.left img{
    position: absolute;
    left:1%;
    top: -5px;
    width: 30px;
    height: 30px;
    margin-right:5px ;
    border-radius: 30px;
   
   
}
#noe{
    width: 80%;
     white-space: nowrap;
    overflow: auto;
    padding-right:5% ;
}
#noe img{
    width: 18vw;
    height: 15vh;
    margin: 5px;

    margin-top: 10px;
}
#no{
    position: absolute;
    right:10%;
    top:40%;
    color: white;
    
    width: 6vw;
}
 #no2{
    position:absolute;
    right: 7%;
    top: 48%;

}
.top{
    position: fixed;
    top:0px;
   left: 5%;
    background: white;
    z-index: 20;
    padding-top: 20px;
}
.red{
    position: absolute;
    top:0px;
    left: 0px;
    width: 100%;
    height: 80vh;
    background: pink;
}
</style>
<template>
  
    <div class="hello" @wheel="gunD" >
        <!-- 添加滚轮事件 -->
       <div class="top" >    <HelloWorld ></HelloWorld></div>
       <div style="height: 10vh;"></div>
    <div class="box" v-if="i">
      <div>
        <div class="left">
            <img src="../assets/img/33333.jpg" alt=""> 
            <b>微信用户</b>
            <span style="color:rgb(124, 124, 121);margin-left: 5px;">体验卡今日到期</span>
        </div>
        <h5 class="right">反馈</h5>
        <div id="noe" >
              <img v-for="(item, index) in arr" :key="index"  @click="boxBtn(item)"    :src="item" alt=""> 
              
        </div>
        <div id="no" @click="Bookstore">书架</div> <img id="no2" src="../assets/img/尖括号111.png" alt="">
      </div>
    </div>
 
    </div>
</template>

<script>
import HelloWorld from './HelloWorld.vue'
export default {
    name: "app",
    mounted(){
        this.$bus.$on("TingS", this.fun)
     this.$bus.$on("xxx", this.fun1)
   },
    data() {
        return {
            show: false,
            i: true,
            n: true,
            tmp:[],
            arr:["https://weread-1258476243.file.myqcloud.com/weread/cover/25/cpplatform_8numzl8erzinxvfsk3p9jv/t6_cpplatform_8numzl8erzinxvfsk3p9jv1685508354.jpg"]
            
        }
    },
    components: {
        HelloWorld,
    },
  
    methods: {//方法
        Bookstore() {
            this.$bus.$emit("abc", {arr:this.arr,id:666})
          
        },
        boxBtn(src) {
            let arr = {
                src: src,
                id:666

            }
            this.tmp.push(arr)
   
            console.log(arr);
        },
        fun(value) {
            if (confirm("要添加到书架吗！！")) {
                     this.arr.unshift(value.src)
               }
       
           
        },
        fun1(value) {
            console.log(value);
            if (value == 1) {
                this.i=false
            } else {
                 this.i = true
             }
        },
        gunD() {
        //     console.log(111111111);
        //  if (event.deltaY > 0) {
        //       this.i=false
        //     } else if (event.deltaY < 0) {
        //      this.i=true
        //     }
        },
    
    },
  
    
    watch: {//监听
        top() {


        },
    },
       computed: {
        //get有什么作用？当有人读取fullName时，get就会被调用，且返回值就作为fullName的值  
        //get什么时候调用？1.初次读取fullName时。2.所依赖的数据发生变化时。  
        // fullName: {
        //     get() {  
               
             
        // }
        // }
    },
    props: {
        msg: String
    }
    
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

