<!--methods
# events
-->
<template>
  <!-- methods -->
  <h2>{{ 2+4+5}}</h2>
  <h2>Add Method - {{ add(4, 6, 7) }}</h2>
  <h2>multiply Method - {{ multiply(5) }}</h2>
  <!-- events -->
  <h2>{{name}}</h2>
  <button v-on:click="changeName($e), increment(1, $e)">Change name</button>

  <h2>{{count}}</h2>
  <div><button v-on:click="increment(1, $event)">increment by 1</button><button v-on:click="decrement(1)">decrement by 1</button></div>
  <div><button @click="increment(5, $event)">increment by 5</button><button @click="decrement(5)">decrement by 5</button></div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data() { return {
    baseMultiplier: 5, name: 'Joram', count: 0,
    
  }},
  //
  methods: {
    // methods
    add(a, b, c) { return a + b + c},
    multiply(num) { return num * this.baseMultiplier },
    // events
    changeName() {this.name = "Dr Strange", console.log('Event', event) },
    increment(num, event) {this.count += num, console.log('Event', event)}, decrement(num) {this.count -= num}
  }
};
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
.underline{text-decoration: underline;}
.promoted{font-style: italic;}
.new{color: green;}
.sold-out{color: red;}
</style>
