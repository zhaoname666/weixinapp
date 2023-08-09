   <style scoped>
* {
   margin: 0;
   padding: 0;
}
.noe{
   background: rgb(243, 237, 237);
     height: 20vh;
     margin: 30px;
      border-radius:10px;
} 
.left{
   width: 40%;
  padding: 10px;
  padding-left :20px; 
   float: left;
   line-height: 30px;

}
p{
   color: rgb(146, 147, 148);
}
img{
   float: right;
   width: 30%;
   height: 20vh;
      border-radius: 0 10px 10px 0;
}
      #loge{
        width: 30px;
        height: 30px;
        margin-left: -10px;
        float:none ;
        margin-left: 40%;
        
     
         }
    </style>
  <template>
     <div class='hello' @scroll="gunD">
      <div  v-for="(item,index) in arr " :key="index" class="noe" >
       <div class="left">
                 <h3>{{ item.name }}</h3>
                 <p>{{ item.text[0]}}</p>
                 <p>{{ item.text[1] }}</p>
                 <p>{{ item.text[2] }}</p>
               </div>
               <img :src="item.img" alt="">
            </div>
           <img id="loge"   src="https://www.aladdiny.com/uploads/loaddata.gif" alt="">
     </div>
  </template>
  <script>
    export default {
     name: 'HelloWorld',
     data() {

          return {
               loge: false,
               arr: [{
                    name: "精品小说",
                    text: ["1.长相思", "2.剑来", "3.三体（全集）"],
                    img:"https://weread-1258476243.file.myqcloud.com/weread/cover/17/yuewen_23484983/t6_yuewen_234849831690286968.jpg"
               },
               {
              name: "历史",
              text: ["1.明朝那些事", "2.唐砖", "3.神话"],
              img: "https://weread-1258476243.file.myqcloud.com/weread/cover/61/YueWen_822995/t6_YueWen_822995.jpg"
                  },
               {
              name: "文学",
              text: ["1.我与地坛", "2.红楼梦", "3.平凡世界"],
              img: "https://wfqqreader-1252317822.image.myqcloud.com/cover/44/674044/t6_674044.jpg"
                  },
               {
              name: "艺术",
              text: ["1.生活蒙太奇", "2.剑来", "3.平凡世界"],
              img: "https://weread-1258476243.file.myqcloud.com/weread/cover/84/YueWen_33514727/t6_YueWen_33514727.jpg"
                  },
               {
              name: "人物",
              text: ["1.长相思", "2.邓小平", "3.李白（全集）"],
              img: "https://wfqqreader-1252317822.image.myqcloud.com/cover/48/674048/t6_674048.jpg"
                  },
               ],
               arr1: [{
             name: "心理学",
              text: ["1.认知觉醒", "2.被讨厌的勇气", "3.影响力"],
              img: "https://weread-1258476243.file.myqcloud.com/weread/cover/41/YueWen_41504771/t6_YueWen_41504771.jpg"
                 }, {
              name: "玄幻",
              text: ["1.统治宇宙", "2.冰河世纪", "3.创生之柱"],
              img: "https://weread-1258476243.file.myqcloud.com/weread/cover/54/YueWen_39457314/t6_YueWen_39457314.jpg"
           }]
           }    
          },
           
            
   methods: {//方法
        gunD(event) {
           let scrollTop = event.target.scrollTop;
           let clientHeight = event.target.clientHeight;
           let scrollHeight = event.target.scrollHeight;
               const scrollPercentage = (scrollTop / (scrollHeight - clientHeight)) * 100;
           let remainingPercentage = 100 - scrollPercentage;
    
           if (Math.ceil(remainingPercentage) == 0) { 
                    this.loge=true
                setTimeout(() => {
                       this.loge = false
                       
                          this.arr.push(...this.arr1)
                  }, 2000)
                     remainingPercentage=30
           }
      
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