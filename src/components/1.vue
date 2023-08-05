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
    </style>
  <template>
     <div class='hello'>
      <div  v-for="(item,index) in arr " :key="index" class="noe" >
       <div class="left">
                 <h3>{{ item.name }}</h3>
                 <p>{{ item.text[0]}}</p>
                 <p>{{ item.text[1] }}</p>
                 <p>{{ item.text[2] }}</p>
               </div>
               <img :src="item.img" alt="">
            </div>
         
     </div>
  </template>
  <script>
    export default {
     name: 'HelloWorld',
     data() {

          return {
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
               ]
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