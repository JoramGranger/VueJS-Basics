<!--watchers
-->
<template>
  <h2>Volume Tracker (0 -20)</h2>
  <h3>Current volume -{{ volume }}</h3>
  <div><button @click="volume += 2">Increase</button><button @click="volume -= 2">Decrease</button></div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
export default {
  name: 'App',
  data() { 
    return {volume: 0}
  },
  // methods
  methods: {},
  // computed
  computed: {},
  watch:{
    volume(newValue, oldValue) {if(newValue > oldValue && newValue === 16){alert('High Volume can damage your ears')}},
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
label {font-weight: bold; display: flex; margin-bottom: 5px;}
input + label { font-weight: bold; display: inline-flex; margin-right: 20px;}
input[type='text'], textarea, select {
  display: block; width: 400px; padding: 6px 12px; font-size: 14px; line-height: 1.4; color: #555; background-color: #fff;
  background-image: none; border: 1px solid #ccc; border-radius: 4px;
}
</style>
