<script>
export default {
  name: 'ChildComponent',
  // 부모에게 데이터를 받는 곳
  props: {
    open: {
      type: Boolean,
      required: true,
    },
  },
  methods: {
    changeColor() {
      this.$emit('show', 'lightpink')
    }
  },
}
</script>




<template>
  <div class="child" :class="{open:open}">
    <button @click="changeColor()" class="c-btn"> 부모 컴포넌트 색상 바꾸기 </button>
  </div>
</template>




<style>
.child {
  position: relative;
  width: 50vw;
  height: 100vh;
  top: 0;
  right:0;
  background-color: cornflowerblue;
  transform: translateX(-100%);
  transition: transform 0.4s cubic-bezier(.71,1.7,.58,.98);
}

.child.open {
  transform: translateX(0%);
}

.c-btn {
  position: absolute;
  width: 60%;
  height: 10%;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  font-size: 1.1rem;
  cursor: pointer;
}

</style>