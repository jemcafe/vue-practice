<template>
  <div class="hello">
    <div class="basics">
      <!-- {{}} interpolation -->
      {{ name }}

      <!-- v-bind:disabled  (Disables the button) -->
      <button v-bind:disabled="btnState">Change Name</button>

      <ul>
        <!-- looping -->
        <!-- <li v-for="(data, index) in skills" :key="index">{{ index }}. {{ data.skill }}</li> -->
      </ul>

      <!-- if / else -->
      <p v-if="skills.length >= 1">You have more than 1 skill</p>
      <p v-else>You have less than or equal to 1 skill</p>

      <!-- class binding  (The classes are binded and the elements are styled if property values are true)-->
      <div v-bind:class="{ alert: showAlert, 'another-class': showClass }"></div>
      <div v-bind:class="alertObject"></div>

      <!-- style binding -->
      <div v-bind:style="{ backgroundColor: bgColor, width: bgWidth, height: bgHeight }"></div>
    </div>

    <!--  -->
    <div class="holder">

      <form @submit.prevent="addSkill">  <!-- the modifier .prevent is basically .prevetDefault() -->
        <input type="text" placeholder="Enter a skill..." v-model="skill">
      </form>

      <ul>
        <li v-for="(data, index) in skills" :key="index">{{ data.skill }}</li>
      </ul>

      <p>The skills you possess</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Skills',  // Component name
  data() {         // State
    return {
      name: 'Bumble',
      btnState: true,
      showAlert: true,
      showClass: true,
      alertObject: {
        alert: true,
        'another-class': true
      },
      bgColor: 'lightblue',
      bgWidth: '100%',
      bgHeight: '30px',

      skills: [
        { "skill": "Vue.js" },
        { "skill": "Front End Developer" },
      ],
      skill: ''
    }
  },
  methods: {
    addSkill: function() {
      this.skills.push({ skill: this.skill });
      this.skill = '';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* <style src="./Skills.css" scoped> */  /* Importing css */
  .basics {
    background: rgb(234, 255, 234); }
  .alert {
    background-color: lightblue;
    width: 100%;
    height: 30px; }
  .another-class {
    border: 2px dashed grey; 
    box-sizing: border-box; }

  /* ------------ */
  .holder {
    margin-top: 20px;
    background: #fff;
  }
  ul {
    margin: 0;
    padding: 0;
    list-style-type: none;
  }
  ul li {
    padding: 20px;
    font-size: 1.3em;
    background-color: #E0EDF4;
    border-left: 5px solid #3EB3F6;
    margin-bottom: 2px;
    color: #3E5252;
  }
  p {
    text-align:center;
    padding: 30px 0;
    color: gray;
  }
  .container {
    box-shadow: 0px 0px 40px lightgray;
  }
  input {
    width: calc(100% - 40px);
    border: 0;
    padding: 20px;
    font-size: 1.3em;
    background-color: #323333;
    color: #687F7F;
  }
</style>
