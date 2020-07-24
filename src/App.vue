<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <button @click="toggleShow">toggle</button>
    <TestTrans v-if="show"/>
    <transition name="trans-fade">
      <div v-if="show">ouside component</div>
    </transition>
  </div>
</template>

<script>
import TestTrans from './components/TestTrans.vue';

export default {
  name: 'App',
  components: {
    TestTrans,
  },
  data() {
    return {
      show: true 
    };
  },
  methods: {
    toggleShow() {
      this.show = !this.show;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}


.trans-fade-enter-active,
.trans-fade-leave-active {
  transition: 0.3s opacity;
}
.trans-fade-enter,
.trans-fade-leave-to {
  opacity: 0;
}
.trans-fade-leave,
.trans-fade-enter-to {
  opacity: 1;
}
</style>
