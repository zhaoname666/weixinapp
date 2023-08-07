   <style scoped>
* {
   margin: 0;
   padding: 0;
}
.hello{
   border-top: 1px solid #f0eded;
    position: fixed;
    bottom: 0%;
    background:white;
width: 110%;
    height: 8vh;
 
}
dl{
   float: left;
   width: 10vw;
   margin: 10px 50px;
   text-align: center;
   color: rgb(187, 184, 184);
   font-size: 12px;
}
img{
   width: 20px;
}
.red{
   color: red;
}
.color{
   color:red
}
    </style>
  <template>
     <div class='hello'>
        <dl @click="btn(1)" :class="i==1?'color':''" >
         <dt><img src="../assets/img/福利.png" alt=""></dt>
         <dd>福利</dd>
        </dl>
         <dl @click="btn(2)" ref="no" :class="i == 2 ? 'color' : ''" >
              <dt><img src="../assets/img/资源 2.png" alt=""></dt>
              <dd>书城</dd>
         </dl>
              <dl @click="btn(3)"   :class="i == 3 ? 'color' : ''">
              <dt><img src="../assets/img/微信图片_20230804172226.png" alt=""></dt>
              <dd>听书</dd>
             </dl>
     </div>
  </template>
  <script>
    export default {
     name: 'HelloWorld',
     data() {
          return {
            i:2
           }
     },
     mounted() {
      
          if (this.i != 2) {
             this.$refs.no.style.color = "";
            } else {
         this.$refs.no.class = "red";
        }
            },
   methods: {//方法
        btn(index) {
           this.i=index
           
             
          }
            },
    watch: {//监听
     op() {
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
<!-- Add 'scoped' attribute to limit CSS to this component only -->