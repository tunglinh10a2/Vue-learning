<template>
  <div id="app">
    <!--<HelloWorld/>-->
    <!--<ComputedProperty></ComputedProperty>-->
    <ClassStyleBinding></ClassStyleBinding>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld'
// import ComputedProperty from './components/ComputedProperty'
import ClassStyleBinding from './components/ClassStyleBinding'

export default {
  name: 'app',
  components: {
    // HelloWorld
    //   ComputedProperty
    ClassStyleBinding
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
