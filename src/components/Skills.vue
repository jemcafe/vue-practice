<template>
  <div class="hello">
    <!-- {{}} interpolation -->
    {{ name }}
    <!-- v-bind:disabled disables the button -->
    <button v-bind:disabled="btnState">Change Name</button>

    <div class="holder">
      <ul>
        <!-- looping -->
        <li v-for="(data, index) in skills" :key="index">{{ index }}. {{ data.skill }}</li>
      </ul>

      <!-- if / else -->
      <p v-if="skills.length >= 1">You have more than 1 skill</p>
      <p v-else>You have less than or equal to 1 skill</p>

      <!-- class binding  (The classes are binded and the elements are styled if property values are true)-->
      <div v-bind:class="{ alert: showAlert, 'another-class': showClass }"></div>
      <div v-bind:class="alertObject"></div>

      <!--  -->
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
      skills: [
        { "skill": "Vue.js" },
        { "skill": "Front End Developer" },
      ],
      showAlert: true,
      showClass: true,
      alertObject: {
        alert: true,
        'another-class': true
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* <style src="./Skills.css" scoped> */  /* Importing css */
  .alert {
    background-color: lightblue;
    width: 100%;
    height: 30px;
  }
  .another-class {
    border: 2px dashed grey;
  }
</style>
