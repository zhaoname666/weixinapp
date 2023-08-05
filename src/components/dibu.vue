   <style scoped>
* {
   margin: 0;
   padding: 0;
}
.hello{
   border-top: 1px solid #999797;
    position: fixed;
    bottom: 0%;
    background:white;
width: 110%;
    height: 10vh;
 
}
dl{
   float: left;
   width: 10vw;
   margin: 10px 50px;
   text-align: center;
   color: rgb(139, 139, 139);
}
    </style>
  <template>
     <div class='hello'>
        <dl>
         <dt><img src="../assets/img/福利.png" alt=""></dt>
         <dd>福利</dd>
        </dl>
         <dl>
              <dt><img src="../assets/img/资源 2.png" alt=""></dt>
              <dd>书城</dd>
         </dl>
              <dl>
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
           }
            },
   methods: {//方法
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