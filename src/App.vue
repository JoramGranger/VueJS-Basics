<!--form handling
-->
<template>
  <form @submit="submitForm">
    <div><prev>{{ JSON.stringify(formValues, null, 2)}}</prev></div>
    <div><label for="name">Name</label><input type="text" id="name" v-model="formValues.name"></div>
    <div><label for="profile">Profile Summary</label><textarea id="profile" v-model="formValues.profileSummary"/></div>
    <div><label for="country">Country</label><select id="country" v-model="formValues.countries">
      <option v-for="country in countries" :key="country" v-bind:value="country">{{country}}</option>
    </select></div>
    <div><label for="job-location">Job Location</label><select id="job-location" multiple v-model="formValues.jobLocation">
      <option v-for="country in countries" :key="country" v-bind:value="country">{{country}}</option>
    </select></div>
    <div><input type="checkbox" id="remoteWork" v-model="formValues.remoteWork" true-value="yes" false-value="no"/><label for="remoteWork">Open to remote work?</label></div>
    <label>Skill Set</label>
    <template v-for="skill in skills" :key="skill">
      <input type="checkbox"  v-bind:id="skill" v-bind:value="skill" v-model="formValues.skillSet" />
      <label v-bind:for="skill">{{skill}}</label>
    </template>
    <label>Year of Experience</label>
    <template v-for="exp in experience" :key="exp">
      <input type="radio"  v-bind:id="exp" v-bind:value="exp" v-model="formValues.experience" />
      <label v-bind:for="exp">{{exp}}</label>
    </template>
    </form>

</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data() { return {
    formValues: {name: '', profileSummary: '', country: '', jobLocation: '', remoteWork: 'no', skillSet: [], experience: ''},
    countries: ['India', 'Vietnam', 'Singapore'], skills: ['css', 'javascript', 'html'], experience: ['0-2', '3-5', '6-10', '10+']
  }},
  //
  methods: {
    submitForm(event){event.preventDefault(), console.log('Form Values', this.formValues)}
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
