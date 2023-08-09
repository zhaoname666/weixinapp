   <style scoped>
* {
   margin: 0;
   padding: 0;
}

ul{
   width: 100%;

   display:flex;
}
ul li {
   width: 18vw;
   list-style: none;
   text-align: center;
   margin-left: 5px;
   color: rgb(97, 96, 96);
}
.hello {
   position: sticky;
   top:20%;
   width: 100%;
   height:100vh;
   background: red;
   overflow-y: scroll;
   background: #fff;
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
#noes{
     position:sticky; 
     top: 0px;
     background: white;
     height: 5vh;
     z-index: 1000;
}
.color{
   color:rgb(78, 159, 226)
}
   #loge{
      height: 50px;
      margin: auto;
   }
    </style>
  <template>
     <div class='hello' ref="no">
      <div id="noes">
        <ul >
         <li :class="i==index ? 'color' : ''"   v-for="(item,index) in arr" :key="index"  @click=" btns(index)"  >{{ item.name }}</li>
        </ul></div>
        <div style="height: 30px;"></div>
        <div class="noe" v-for="(item,index) in arr[i].text" :key="index" >
       <div @click.once="fun(item)" class="no" v-if="s" >
           <img :src="item.src" alt="" class="imgs">
           <div style="width: 10px;height: 20px;" ></div>
              <h3 style="margin: 10px;">{{ item.name }}</h3>
              <pre>{{  item.text}} | 推荐值 {{ item.n }}%  <b v-if="item.status" style="color:red">{{item.html}}</b></pre>
              <p>大家都在读</p>
   
       </div>
       </div>
       <div v-if="no1">
         <No1/>
       </div>
       <div v-if="no2">  <No2/></div>
       <div  v-if="no3">  <No3/></div>
          <div  v-if="no4">  <No4/></div>
          
      <div style="width: 100%;text-align: center;margin-bottom: 50px;" v-if="loge" >
            <img id="loge" v-if="loge"  src="https://www.aladdiny.com/uploads/loaddata.gif" alt="">
             <!-- <div v-if="loge1" style="color: red;">加载失败</div>  -->
         </div>
      </div>
    
  </template>
  <script>
  import No1 from './1.vue'
  import No2 from './2.vue'
  import No3 from './3.vue'
  import No4 from './4.vue'



    export default {
     name: 'HelloWorld',
       components: {
            No1,
            No2,
            No3,
             No4,
           
         
     },
     data() {
          return {
               loge: false,
            loge1:false,
               ss: false,
              sc:false,
               no1: false,
               no2: false,
               no3: false,
               no4: false,
               s: true,
               i: 0,
               n: false, 
            

               
               arr: [

                  {
                     name: "推荐",

                     status: false,
                     text: [{

                        name: "资本的秘密",
                        src: "https://weread-1258476243.file.myqcloud.com/weread/cover/25/cpplatform_8numzl8erzinxvfsk3p9jv/t6_cpplatform_8numzl8erzinxvfsk3p9jv1685508354.jpg",
                        text: "赫尔南多·德·索托",
                        n: 89.8,
                        status: false,
                        html: "好评如潮",

                     },

                     {

                        name: "天工开物",
                        src: "https://weread-1258476243.file.myqcloud.com/weread/cover/75/cpplatform_vkins1c9mzkmfbt3kjlrn9/t6_cpplatform_vkins1c9mzkmfbt3kjlrn91677476708.jpg",
                        text: "宋莹星",
                        n: 97.6,
                        status: false,
                        html: "神作",
                     },
                     {

                        name: "法医秦明：白卷",
                        src: "https://weread-1258476243.file.myqcloud.com/weread/cover/55/cpplatform_2thuj2jlv1odkiylmdlcjr/t6_cpplatform_2thuj2jlv1odkiylmdlcjr1689825647.jpg",
                        text: "法医秦明",
                        n: 78.6,
                        status: false,
                        html: "好评如潮",
                     },
                     {

                        name: "长安的荔枝",
                        src: "https://weread-1258476243.file.myqcloud.com/weread/cover/75/cpPlatform_dbb14284a55f1e733b60202b0777255d/t6_cpPlatform_dbb14284a55f1e733b60202b0777255d.jpg",
                        text: "马伯庸",
                        n: 50.8,
                        status: false,
                        html: "废材",
                     },
                     {

                        name: "活着",
                        src: "https://wfqqreader-1252317822.image.myqcloud.com/cover/464/834464/t6_834464.jpg",
                        text: "余华",
                        n: 99.8,
                        status: false,
                        html: "神作",
                     },
                     {

                        name: "从文自传",
                        src: "https://wfqqreader-1252317822.image.myqcloud.com/cover/791/36059791/t6_36059791.jpg",
                        text: "从文",
                        n: 60.8,
                        status: false,
                        html: "废材",
                     },
                     {

                        name: "挣脱",
                        src: "https://weread-1258476243.file.myqcloud.com/weread/cover/9/cpplatform_ffxxfh9zishrhh1gdece8z/t6_cpplatform_ffxxfh9zishrhh1gdece8z1690196853.jpg",
                        text: "刘仁霞",
                        n: 89.8,
                        html: "好评如潮",
                     },
                     {

                        name: "上等快乐",
                        src: "https://weread-1258476243.file.myqcloud.com/weread/cover/43/cpplatform_uksuobynut7k8guvdp7jpb/t6_cpplatform_uksuobynut7k8guvdp7jpb1690794764.jpg",
                        text: "打野来了",
                        n: 60,
                        status: false,
                        html: "废材",

                     },

                     ]
                  },
                  {
                     name: "分类",
                     id: 2,
                     status: false,
                   text: [{

                        name: "资本的秘密",
                        src: "https://weread-1258476243.file.myqcloud.com/weread/cover/25/cpplatform_8numzl8erzinxvfsk3p9jv/t6_cpplatform_8numzl8erzinxvfsk3p9jv1685508354.jpg",
                        text: "赫尔南多·德·索托",
                        n: 89.8,
                        status: false,
                        html: "好评如潮",

                     }],
                  },
               {
                 name: "排行",
                 id: 1,
                 status: false,
                  },
               {
                 name: "文学艺术",
                 id: 1,
                 status: false,
                  },
               {
                 name: "哲学社科",
                 id: 1,
                 status: false,
              },
                     
                  ],

           }
     },
          
     destroyed() {
        this.$refs.no.removeEventListener('scroll', this.handleScroll);
     },
   methods: {//方法
        btns(value) {
             
             this.i=value
         
      },
        fun(value) {
         this.$bus.$emit("TingS",value)
      },
        handleScroll() {
         let sss= [{

              name: "从文自传",
              src: "https://wfqqreader-1252317822.image.myqcloud.com/cover/791/36059791/t6_36059791.jpg",
              text: "从文",
              n: 60.8,
              status: false,
              html: "废材",
           },
           {

              name: "挣脱",
              src: "https://weread-1258476243.file.myqcloud.com/weread/cover/9/cpplatform_ffxxfh9zishrhh1gdece8z/t6_cpplatform_ffxxfh9zishrhh1gdece8z1690196853.jpg",
              text: "刘仁霞",
              n: 89.8,
              html: "好评如潮",
           },
           {

              name: "上等快乐",
              src: "https://weread-1258476243.file.myqcloud.com/weread/cover/43/cpplatform_uksuobynut7k8guvdp7jpb/t6_cpplatform_uksuobynut7k8guvdp7jpb1690794764.jpg",
              text: "打野来了",
              n: 60,
              status: false,
              html: "废材",

              },
           
           ]
          
        const scrollHeight = this.$refs.no.scrollHeight;
           const scrollTop = this.$refs.no.scrollTop;
           const clientHeight = this.$refs.no.clientHeight;

           const scrollPercentage = (scrollTop / (scrollHeight - clientHeight)) * 100;
           let remainingPercentage = 100 - scrollPercentage;
             if (Math.ceil(remainingPercentage) == 0) {
            
                this.loge = true
                  this.loge1 = false
            setTimeout(() => {
               this.loge = false
                 this.loge1 = true
             
                 this.arr[0].text.push(...sss)
             
            }, 3000)
                remainingPercentage = 20
            
         
             } 
        }
        
            },
    watch: {//监听
         i() {
            this.no1 = false
           this.no2=false
            this.no3 = false
            this.no4 = false
            this.s = false
             
              
             switch (this.i) {
              case 0:
                     this.s = true

                     break;
                  case 1:
                     this.no1 = true
                     break;
                   case 2:
                     this.no2 = true
                     break;
                   case 3:
                   this.no3= true
                     break;
                   case 4:
                 this.no4 = true
                 break;                
            }
      
           },
       
           },
     computed: {
//get有什么作用？当有人读取fullName时，get就会被调用，且返回值就作为fullName的值  
//get什么时候调用？1.初次读取fullName时。2.所依赖的数据发生变化时。

     },
     mounted() {
          this.$refs.no.addEventListener('scroll', this.handleScroll);
   
          this.arr[0].text.forEach((item) => {
           
                    item.status = true
              
             
             
                
      })
   
     },
     props: {
    msg: String
           }
}
     </script>
<!-- Add 'scoped' attribute to limit CSS to this component only -->