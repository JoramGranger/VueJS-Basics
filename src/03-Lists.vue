<!--list rendering
-->
<template>
  <h2 v-for="(name, index) in names" :key="name">{{ index+1 }} {{ name }}</h2> <!-- for arrays -->
  <h2 v-for="name in fullNames" :key="name.first">{{ name.first }} {{ name.last }}</h2>  <!-- for array of objects -->
  <div v-for="actor in actors" :key="actor.name">  <!-- for array of arrays/objects -->
    <h2>{{actor.name}}</h2> <h3 v-for="movie in actor.movies" :key="movie.movies">{{movie}}</h3>
  </div>
  <h2 v-for="(value, key, index) in myInfo" :key="value">{{ index+1 }} {{ key }} {{ value }}</h2>  <!-- for objects -->

  <!-- list with separators -->
  <template v-for="name in names" :key="name"> <!-- with separators -->
    <h2>{{name}}</h2> 
    <hr />
  </template>
  <!-- conditional list rendering -->
  <template v-for="name in names" :key="name">
    <h2 v-if="name === 'bruce'">{{ name }}</h2>
  </template>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data() { return {
    names: ['bruce', 'clark', 'diana'],
    fullNames: [{first: 'Stephen', last: 'Strange'}, {first: 'America', last: 'Charvez'}, {first: 'Wanda', last: 'Maximoff'}],
    actors: [{name: 'Tom Holland', movies: ['spider-man', 'unchattered']}, {name: 'Mia Gonzalez', movies: ['ambulance', 'bloodshot']}],
    myInfo: { name: 'Joram', team: 'group 10', task: 'frontend'},
  }},
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
