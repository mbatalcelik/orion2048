<template>
  <div class="row icon-container boxes">
    <box v-for="(box, index) in boxs" v-bind:key="index" v-bind:boxData="box" />
  </div>
</template>

<script>
import { onMounted, ref } from "vue";
import box from "./box/box.vue";

export default {
  components: { box },
  name: "HelloWorld",
  props: {
    msg: String,
  },
  setup() {
    const leng = ref(4);
    const boxs = ref([]);
    onMounted(function () {
      for (let i = 0; i < leng.value; i++) {
        for (let c = 0; c < leng.value; c++) {
          const box = ref({ x: i, y: c, value: 0 });
          boxs.value.push(box);
        }
      }
      window.addEventListener("keyup", move);
    });
    function move(e) {
      // eslint-disable-next-line no-empty
      if (e.key == "ArrowUp") {
      } else if (e.key == "ArrowLeft") {
        console.log(e);
      } else if (e.key == "ArrowRight") {
        console.log(e);
      } else if (e.key == "ArrowDown") {
        console.log(e);
      }
      console.log(e);
    }

    return {
      boxs,
    };
  },
};
</script>

<style scoped>
.boxes {
  width: 400px;
  height: 400px;
}
.box {
  border: 1px solid;
  border-radius: 5px;
  width: 100px;
  height: 100px;
  text-align: center;
  vertical-align: middle;
  line-height: 100px;
  font-size: 50px;
  font-weight: bold;
  float: left;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
