<template>
  <div id="app">
    <TopHeader />
    <ListOfTweets />
  </div>
</template>

<script>
import ListOfTweets from './components/ListOfTweets.vue'
import TopHeader from './components/TopHeader.vue'

export default {
  name: 'App',
  components: {
    ListOfTweets,
    TopHeader
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  overflow-x: hidden;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: rgb(54, 54, 54);
}
</style>
