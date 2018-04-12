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
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
