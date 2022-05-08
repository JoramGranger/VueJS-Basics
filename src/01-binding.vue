<!--binding text-->
<template>
<div>{{greet}} {{name}}</div> <!-- mustache -->
<div v-text="devside"></div> <!-- v-text directive -->
<div v-html="team"></div> <!-- v-html directive -->
<div v-html="hack"></div> <!-- mustache -->

<!--binding attributes-->
<h2 v-bind:id="headingId">Heading</h2>
<button v-bind:disabled="isDisabled">Submit</button> 
<h2 class="underline">Underlined text</h2> <!-- static classes -->
<h2 v-bind:class="status">Status</h2> <!-- dynamic classes-->
<h2 class="underline" v-bind:class="status">State</h2> <!-- dynamic classes and static classes combined-->
<h2 v-bind:class="isPromoted && 'promoted'">Promoted movie</h2>
<h2 v-bind:class="isSoldOut ? 'sold-out' : 'new'">Soldout Movie</h2> <!-- conditional class binding-->
<h2 v-bind:class="['new', 'promoted']">New and Promoted movie</h2> <!-- array of class binding-->
<h2 v-bind:class="[isPromoted && 'promoted', isSoldOut ? 'sold-out' : 'new']">New or Soldout and Promoted movie</h2> <!-- conditional array of class binding-->
<h2 v-bind:class="{
  promoted: isPromoted,
  new: !isSoldOut,
  'sold-out': isSoldOut
}">New or Soldout and Promoted movie</h2> <!-- conditional object of class binding-->
<!-- Binding Style -->
<h1 v-bind:style="{color: highLightColor, 'font-size': headerSize + 'px', padding: '20px'}">Inline Style</h1> <!-- various styles -->
<h1 v-bind:style="headerStyleObject">object style</h1>
<h1 v-bind:style="[baseStyle, successStyleObject]">Sucess style</h1>
<h1 :style="[baseStyle, dangerStyleObject]">danger style</h1>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data(){return {greet: "Hello", name: "Joraneuve", devside: "front end", team: "<b>group 11<b>",
  hack: `<a href="#" onclick="alert('You have been hacked!')">Win a prize</a>`,
  headingId: 'heading', isDisabled: false, status: 'danger', isPromoted: true, isSoldOut: true,
  highLightColor: 'orange', headerSize: 50,
  headerStyleObject: { color: 'orange', fontSize: '50px', padding: '20px'},
  baseStyle: { fontSize: '50px', padding: '10px'},
  successStyleObject: { color: 'green', backgroundColor: 'lightgreen', border: '1px solid green',},
  dangerStyleObject: { color: 'darkred', backgroundColor: 'red', border: '1px solid darkred'},
  };},
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
