<script>
import ChildComponent from "@/components/ChildComponent.vue";

export default {
  name: "App",
  components: {ChildComponent},
  data() {
    return {open:false, backColor:'lemonchiffon'}
  },
  methods: {
    show(color) {
      this.backColor = color;
    },
    child() {
      this.open = !this.open;
    }
  }
}
</script>



<template>
<div class="app" :style="{backgroundColor: backColor}">
  <button class="p-btn" @click="child"> 자식 컴포넌트 나타나기 </button>
  <ChildComponent :open="open" @show="show"/>
</div>
</template>



<style>
.app {
  position: relative;
  width: 100vw;
  height: 100vh;
}

.p-btn {
  position: absolute;
  width: 30%;
  height: 10%;
  top: 50%;
  left: 75%;
  transform: translate(-50%, -50%);
  text-align: center;
  font-size: 1.1rem;
  z-index: 2;
  cursor: pointer;
}
</style>
