<style scoped>
* {
    margin: 0;
    padding: 0;
}
.box{
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
    float: left;
}
.right{
    float: right;
    margin-right: -20px;;
}
b{
    color:white;
 

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

</style>
<template>
    <div class="hello">
    <div class="box">
      <div>
        <div class="left">
            <img src="" alt=""> 
            <b>微信用户</b>
            <span style="color:rgb(124, 124, 121);margin-left: 5px;">体验卡今日到期</span>
        </div>
        <h5 class="right">反馈</h5>
       
      </div>
    </div>

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

