<template>
  <div id="app">
    <table-data></table-data>
  </div>
</template>

<script>


import TableData from "./views/TableData";

export default {
  name: 'app',
  components: {TableData},
  comments:{
    TableData
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
