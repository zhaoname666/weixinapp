   <style scoped>
* {
   margin: 0;
   padding: 0;
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
               position: relative;
 
         }
         .no pre, p{
            font-size: 10px;
            color: rgb(131, 127, 127);
         }
           #loge{
            position: absolute;
            left: 88%;
            top: 9%;
            width: 20vw;
            height: 3vh;
            text-align:left;
            background: rgb(235, 234, 234);
            font-size: 6px;
            color: rgb(129, 130, 131);
            line-height: 1px;
            border-radius: 15px;
         }
    </style>
  <template>
     <div class='hello' @scroll="gunD">
          <div class="no" v-for="(item, index) in arr" :key="index"  >
                     <img :src="item.src" alt="" class="imgs">
                     <div style="width: 10px;height: 20px;" ></div>
                        <h3 style="margin: 10px;">{{ item.name }}</h3>
                        <pre>{{ item.text }} </pre>
                        <p> 推荐值 {{ item.n }}%  <b v-if="item.status" style="color:red">{{ item.html }}</b></p>
                          <div id="loge"> <img style="margin-left: 12px;margin-top: 2px;     vertical-align: text-bottom;" src="../assets/img/账户.png" alt=""> <span>2965</span></div>
   
                 </div>
     </div>
  </template>
  <script>
    export default {
     name: 'HelloWorld',
     data() {
          return {
        arr: [
              {

                 name: "资本的秘密",
                 src: "https://weread-1258476243.file.myqcloud.com/weread/cover/25/cpplatform_8numzl8erzinxvfsk3p9jv/t6_cpplatform_8numzl8erzinxvfsk3p9jv1685508354.jpg",
                 text: "赫尔南多·德·索托",
                 n: 89.8,
                 status: true,
                 html: "好评如潮",

              },

              {

                 name: "天工开物",
                 src: "https://weread-1258476243.file.myqcloud.com/weread/cover/75/cpplatform_vkins1c9mzkmfbt3kjlrn9/t6_cpplatform_vkins1c9mzkmfbt3kjlrn91677476708.jpg",
                 text: "宋莹星",
                 n: 97.6,
                 status: true,
                 html: "神作",
              },
              {

                 name: "法医秦明：白卷",
                 src: "https://weread-1258476243.file.myqcloud.com/weread/cover/55/cpplatform_2thuj2jlv1odkiylmdlcjr/t6_cpplatform_2thuj2jlv1odkiylmdlcjr1689825647.jpg",
                 text: "法医秦明",
                 n: 78.6,
                 status: true,
                 html: "好评如潮",
              },
              {

                 name: "长安的荔枝",
                 src: "https://weread-1258476243.file.myqcloud.com/weread/cover/75/cpPlatform_dbb14284a55f1e733b60202b0777255d/t6_cpPlatform_dbb14284a55f1e733b60202b0777255d.jpg",
                 text: "马伯庸",
                 n: 50.8,
                 status: true,
                 html: "废材",
              },
              {

                 name: "活着",
                 src: "https://wfqqreader-1252317822.image.myqcloud.com/cover/464/834464/t6_834464.jpg",
                 text: "余华",
                 n: 99.8,
                 status: true,
                 html: "神作",
              },
              {

                 name: "从文自传",
                 src: "https://wfqqreader-1252317822.image.myqcloud.com/cover/791/36059791/t6_36059791.jpg",
                 text: "从文",
                 n: 60.8,
                 status: true,
                 html: "废材",
              },
           ]
           }
            },
   methods: {//方法
       gunD(event) {
           let scrollTop = event.target.scrollTop;
           let clientHeight = event.target.clientHeight;
           let scrollHeight = event.target.scrollHeight;
           const scrollPercentage = (scrollTop / (scrollHeight - clientHeight)) * 100;
           let remainingPercentage = 100 - scrollPercentage;
           console.log(Math.ceil(remainingPercentage));
           if (Math.ceil(remainingPercentage) == 0) {
              this.arr.push(...this.arr)
              setTimeout(() => {
                 remainingPercentage = 60
              }, 2000)
           }
        },
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