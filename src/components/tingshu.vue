   <style scoped>
           * {
              margin: 0;
              padding: 0;
              }
              .hello{
                width: 90%;

                   height: 1000px;
                   margin: auto;
              }
              .no{
          
            width: 80%;
            margin: 20px;
            min-height: 20vh;
            line-height: 20px;
 
         }
              img{
            width: 20vw;
            height: 18vh;
            float: left;
            margin-right: 10px;
 
         }
         .noe{
            margin-top: 20px;
            width: 80%;
            height: 20vh;
            color:rgb(177, 178, 179)
         }
         p{
            font-size: 10px;
            margin: 10px 0;
         }
         .p1{
            font-size:16px;
            color:rgb(112, 110, 109)
         }
         .div-btn{
            width: 80%;
            height: 5vh;
            color:rgb(112, 110, 109) ;
            background: rgb(224, 222, 222);
            text-align: center;
            line-height:5vh;
            margin: auto;
            border-radius: 5px;
         }
          #loge{
           width: 30px;
           height: 30px;
           margin-left: -10px;
           float:none ;
           margin-left: 40%;
        
     
            }
             .n{
         width: 100%;
           text-align: center;
           margin-bottom: 10px;
      }
    </style>
  <template>
     <div class='hello'>
      <div   class="no" v-for="(item,index) in arr" :key="index">
       <h3>{{ item.html }}</h3> 
       <div @click="fun(index,b)" style="" class="noe" v-for="(a,b) in item.tmp" :key="b">
        <img :src="a.src" alt="">
         <div style="width: 10px;height: 10px;" ></div>
         <p class="p1">{{ a.name }}</p>
          <pre>{{ a.text }} | 七猫小说</pre>
          <p> {{ a.ren }} 人今日在听</p>   
       </div>
         <img id="loge"   src="https://www.aladdiny.com/uploads/loaddata.gif" alt="">
         <p class="n"  >加载失败</p>
       <div class="div-btn" >查看更多</div>
      </div>
      
     </div>
  </template>
<script>
    export default {
         name: 'HelloWorld',
          data() {
              return {
                  arr: [{
                      html: "影视热门榜",
                      tmp: [{

                    name: "庆余年",
                    src: "https://weread-1258476243.file.myqcloud.com/weread/cover/25/cpplatform_8numzl8erzinxvfsk3p9jv/t6_cpplatform_8numzl8erzinxvfsk3p9jv1685508354.jpg",
                    text: "猫腻",
                    status: true,
                    html: "好评如潮",
                    ren:348,

                },

                {

                    name: "鬼吹灯（盗墓者的经历）",
                    src: "https://weread-1258476243.file.myqcloud.com/weread/cover/75/cpplatform_vkins1c9mzkmfbt3kjlrn9/t6_cpplatform_vkins1c9mzkmfbt3kjlrn91677476708.jpg",
                    text: "本物天下霸唱",
                    n: 97.6,
                    status: true,
                   html: "神作",
                     ren: 119,
                },]
                  },
                  {
                html: "免费榜",
                tmp: [{

                    name: "斗破苍穹",
                    src: "https://weread-1258476243.file.myqcloud.com/weread/cover/25/cpplatform_8numzl8erzinxvfsk3p9jv/t6_cpplatform_8numzl8erzinxvfsk3p9jv1685508354.jpg",
                    text: "天蚕土豆",
                    status: true,
                   html: "好评如潮",
                    ren: 33,

                },

                {

                    name: "龙须",
                    src: "https://weread-1258476243.file.myqcloud.com/weread/cover/75/cpplatform_vkins1c9mzkmfbt3kjlrn9/t6_cpplatform_vkins1c9mzkmfbt3kjlrn91677476708.jpg",
                    text: "暖秋",
                    n: 97.6,
                    status: true,
                   html: "神作",
                    ren: 22,
                },]
            }]
           }
            },
   methods: {//方法
      fun(index,b) {
    
         this.$bus.$emit("TingS", this.arr[index].tmp[b])
               
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