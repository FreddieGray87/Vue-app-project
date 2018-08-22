<template>
  <div id="app">
  <h1>{{message}}</h1>
<a v-on:click="handleClick">Clickme!</a>
  <p>My first App!</p>
  <circle-slider v-model="val1"></circle-slider>
  <div>{{ val1 }}</div>
<router-view/>
<dropdown :options="arrayOfObjects" :selected="selectedObject" v-on:updateOption="updateSelected"></dropdown>
</div>
</template>

<script>
import hello from "./views/HelloWorld";
// import dropdown from "vue-dropdowns";
import Cal from "./views/tipCal";
export default {
  name: "app",
  data() {
    return {
      message: "Climbing Grade Converter!",
  //     arrayOfObjects: [
  //       { id: 1, name: "First Option" },
  //       { id: 2, name: "Second Option" },
  //       { id: 3, name: "Third Option" }
  //     ],
  //     selectedObject: {}
  //   };
  // },
  // components: {
  //   dropdown: dropdown
  // },
  // methods: {
  //   updateSelected(payload) {
  //     this.selectedObject = payload;
  //   }
  // },
  // methods: {
  //   handleClick: function() {
  //     alert("test");
  //   }
  // }
}}};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
