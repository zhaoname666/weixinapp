<template>
  <div id="app">
    <div v-show="myid">
      <div class="top"><Card /></div>
      <Labels v-show="n" />
      <Buttos />
      <TingShu v-show="ts" />
      <FuLi v-show="f" />
    </div>
    <div v-show="ins">
      <h4>
        《书架全部图书》<b
          style="float: right; font-size: 20px"
          @click.stop="btnOdd"
          >》</b
        >
      </h4>
      <div class="noe" v-for="(item, index) in arr" :key="index">
        <h3>第{{ index + 1 }}本</h3>
        <img :src="item" alt="" /><br />
        <button @click="btnGo">立即阅读</button>
      </div>
    </div>
  </div>
</template>

<script>
import Card from "./components/体验卡.vue";
import Labels from "./components/biaoqianye.vue";
import Buttos from "./components/dibu.vue";
import TingShu from "./components/tingshu.vue";
import FuLi from "./components/fuli.vue";

export default {
  name: "App",
  data() {
    return {
      ins: true,
      ns: 1,
      f: false,
      i: 2,
      n: false,
      ts: false,
      id: null,
      myid: true,
      arr: [],
    };
  },
  mounted() {
    this.$bus.$on("xxx", this.demo);
    this.$bus.$on("abc", this.Bookstore);

    if (this.i == 2) {
      this.n = true;
      this.myid = true;
    }
  },
  methods: {
    btnGo() {
      alert("内部错误，无法加载");
    },
    btnOdd() {
      this.myid = true;
    },
    Bookstore(value) {
      this.id = value.id;
      this.arr = value.arr;
      console.log(this.arr);

      if (this.id != null) {
        this.myid = false;
      } else {
        this.myid = true;
      }
      if (this.i == 1) {
        this.f = true;
      }
      if (this.i == 2) {
        this.n = true;
      }
    },
    demo(value) {
      this.i = value;
      this.n = false;
      this.ts = false;
      this.f = false;

      switch (this.i) {
        case 1:
          this.f = true;
          break;
        case 2:
          this.n = true;
          break;
        case 3:
          this.n = false;
          this.ts = true;
          break;
        default:
          break;
      }
    },
  },
  components: {
    Card,
    Labels,
    Buttos,
    TingShu,
    FuLi,
  },
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
}
h3 {
  color: aqua;
}
h4 {
  text-align: center;
  color: pink;
}
.noe {
  width: 70%;
  margin: 20px auto;
  text-align: center;
  background: salmon;
  padding: 20px;
  border-radius: 10px;
}
.top {
  z-index: 2;
}
#app {
  /* overflow: hidden; */
}
img {
  width: 40%;
}
button {
  width: 40%;
  height: 30px;
  border: none;
}
</style>
