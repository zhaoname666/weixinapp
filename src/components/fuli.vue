   <style scoped>
* {
  margin: 0;
  padding: 0;
}
.box{
    position: relative;
    width: 90%;
    margin: 50px auto;
    min-height: 10vh;
    background:white;
     box-shadow: 0px 2px 10px rgba(0, 0, 0, 0.5);
     border-radius: 10px 10px 0 0;
}
img{
    width: 100%;
    height: 200px;
    border-radius: 10px 10px 0 0;
}
p,h3{

    padding-top: 20px;
    padding-left: 10%;
}
p{
padding-bottom: 20px;
color: #ccc;
font-size: 10px;
}
button{
    position: absolute;
    bottom: 10%;
    left: 70%;
    /* transform: translate(-50%,0); */
   width: 20vw;
   height: 4vh;
   border-radius: 10px;
   background: rgb(233, 183, 118);
   border:none;
}
</style>
  <template>
  <div class="hello">
    <div class="box" v-for="(item,index) in arr" :key="index">
        <img :src="item.src" alt="">
        <h3>{{ item.name }}</h3>
        <p>{{ item.text }}</p>
        <button>{{ item.btn }}</button>
    </div>
  </div>
</template>
<script>
export default {
  name: "HelloWorld",
  data() {
      return {
          arr: [{
              name: "每日一答",
              text: "挑战连续答对12道题",
              src: "https://img2.baidu.com/it/u=3685310330,1976104907&fm=253&fmt=auto?w=130&h=170",
              
              btn:"玩一玩"
          }, {
                name: "读书小队",
                text: "俩人成对,共攒积分大奖",
                src: "https://img0.baidu.com/it/u=3802419703,1735441684&fm=253&fmt=auto&app=138&f=PNG?w=200&h=200",

                btn: "立即组队"
            }, {
                name: "免费图书馆",
                text: "时间 08.10-08.17",
                src: "https://img1.baidu.com/it/u=786599046,1257041463&fm=253&fmt=auto&app=120&f=JPEG?w=190&h=190",

                btn: "立即查看"
            }]
    };
  },
  methods: {
    //方法
  },
  watch: {
    //监听
    op() {},
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
    msg: String,
  },
};
</script>
<!-- Add 'scoped' attribute to limit CSS to this component only -->