<!--computed properties
-->
<template>
  <h2>Fullname - {{ fname }} {{ lname }}</h2>
  <h2>computed Fullname - {{ fullName }}</h2>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data() { return {
    fname: 'Stephen', lname: 'Strange',
    items: [{id: 1, title: 'TV', price: 100,}, {id: 2, title: 'phone', price: 200,}, {id: 3, title: 'laptop', price: 300,}],  
  }},
  //
  methods: {
        
  },
  computed: {
      fullName() {return `${this.fname} ${this.lname}`}
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
