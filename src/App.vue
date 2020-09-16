<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    {{listFacilitys}}

    {{listCourse_packages}}
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
// brought in gql for apollo stuff
import gql from 'graphql-tag'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  apollo: {
    // Simple query that will update the 'hello' vue property
    listFacilitys: gql`query {
      listFacilitys {
        id
        name
      }
    }`,
    listCourse_packages: gql`query {
      listCourse_packages {
        name
      }
    }`,
  },
}
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
</style>
