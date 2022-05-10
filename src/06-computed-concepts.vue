<!--computed properties
-->
<template>
  <h2>Fullname - {{ fname }} {{ lname }}</h2>
  <h2>computed Fullname - {{ fullName }}</h2>
  <!-- computed setter and getter -->
  <button @click="changeFullName()">Change FullName</button>
  <button @click="items.push({id: 4, title: 'keyboard', price: 50})">Add item</button>
  <h2>total - {{ total }}</h2>
  <h2>total - {{ getTotal() }}</h2> <!-- using method -->
  <input type="text" v-model="country">

  <!-- computed without v-for -->
  <template v-for="item in items" :key="item">
    <h2 v-if="item.price > 100">{{item.title}} {{item.price}}</h2>
  </template>
  <!-- computed with v-for -->
  <template v-for="item in expensiveItems" :key="item.id">
    <h2><b>{{item.title}} {{item.price}}</b></h2>
  </template>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
export default {
  name: 'App',
  data() { return {
    fname: 'Stephen', lname: 'Strange',
    items: [{id: 1, title: 'TV', price: 100,}, {id: 2, title: 'phone', price: 200,}, {id: 3, title: 'laptop', price: 300,}],
    country: '', 
  }},
  //
  methods: {
    getTotal(){console.log('getTotal Method') 
    return this.items.reduce((total, curr) => (total = total + curr.price), 0)},
    changeFullName(){this.fullName = 'Peter Parker'},
  },
  computed: {
      fullName: { 
        get() {return `${this.fname} ${this.lname}`}, 
        set(value){
          const names = value.split(' ') 
          this.fname = names[0] 
          this.lname = names[1]}},
      //fullName() {return `${this.fname} ${this.lname}`},
      total() {console.log('total computed property') 
      return this.items.reduce((total, curr) => (total = total + curr.price), 0)},
      expensiveItems() {return this.items.filter(item => item.price > 100)},
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
