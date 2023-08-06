   <style scoped>
* {
   margin: 0;
   padding: 0;
}
.hello{
    widows: 100px;

    height:100px;
    background: red;
}
h1{
   margin: 20px;
   padding-left:20px ;
   color: red;
}
img{
  width: 20vw;
 
      margin-right: 10px;
}
.noe{
   margin: 10px;
}

   .imgs{
      width: 20vw;
      float: left;
      margin-right: 10px;
 
   }
   .no{
      width: 80%;
      margin: 20px;
      min-height: 20vh;
      line-height: 20px;
 
   }
   .no pre, p{
      font-size: 10px;
      color: rgb(131, 127, 127);
   }
   #btn{
      width: 80%;
      height: 30px;
      background: #ccc;
      margin: auto;
      line-height: 30px;
      margin-bottom:50px ;
      text-align: center;
      border-radius: 5px;
      color: #696666;
   }
   h6{
      width: 100%;
     text-align: center;
      margin: 10px;
   }
   .n{
      width: 100%;
        text-align: center;
        margin-bottom: 10px;
   }
    </style>
  <template>
     <div class='hello'>
              <h1>top50 /飙升榜</h1>
              <div class="no" v-for="(item,index) in arr" :key="index" >
                <img :src="item.src" alt="" class="imgs">
                <div style="width: 10px;height: 20px;" ></div>
                   <h3 style="margin: 10px;">{{ item.name }}</h3>
                   <pre>{{ item.text }}</pre>
                   <p>大家都在读</p>
   
            </div>
            <div v-if="n">
               <h6 v-if="i" >  <img src="https://www.aladdiny.com/uploads/loaddata.gif" alt=""></h6>
                   <p class="n" v-else >加载失败</p>  
            </div>
         
          <div id="btn" @click="btn">查看全部</div>
        
     </div>
  </template>
  <script>

    export default {
     name: 'HelloWorld',
     data() {
          return {
               i: false,
            n:false,
               arr: [
         {

                 name: "1 资本的秘密",
                 src: "https://weread-1258476243.file.myqcloud.com/weread/cover/25/cpplatform_8numzl8erzinxvfsk3p9jv/t6_cpplatform_8numzl8erzinxvfsk3p9jv1685508354.jpg",
                 text: "赫尔南多·德·索托",
                 n: 89.8,
                 status: false,
                 html: "好评如潮",

              },

              {

                 name: "2 天工开物",
                 src: "https://weread-1258476243.file.myqcloud.com/weread/cover/75/cpplatform_vkins1c9mzkmfbt3kjlrn9/t6_cpplatform_vkins1c9mzkmfbt3kjlrn91677476708.jpg",
                 text: "宋莹星",
                 n: 97.6,
                 status: false,
                 html: "神作",
              },
              {

                 name: "3  法医秦明：白卷",
                 src: "https://weread-1258476243.file.myqcloud.com/weread/cover/55/cpplatform_2thuj2jlv1odkiylmdlcjr/t6_cpplatform_2thuj2jlv1odkiylmdlcjr1689825647.jpg",
                 text: "法医秦明",
                 n: 78.6,
                 status: false,
                 html: "好评如潮",
              },
      ]
           }
     },
               mounted() {
        this.arr.forEach((item) => {
           item.status = true

        })

     },
   methods: {//方法
        btn() {
         this.n=true
         this.i=true
         setTimeout(() => {
        this.i=false

          
         }, 3000)

         
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