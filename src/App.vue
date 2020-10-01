<template>
  <div id="app">
    <img
      src="https://media.giphy.com/media/o0vwzuFwCGAFO/giphy.gif"
      class="rounded-circle"
      width="240"
    />
    <p></p>
    <giphy />
  </div>
</template>

<script>
import Giphy from "./components/Giphy.vue";

export default {
  name: "App",
  components: {
    Giphy,
  },
};
</script>

<style>
#app {
  background-image: url(https://rawpixel-live.imgix.net/collection/cover/99bf1f74fb0cfc223e186b946c7135dd_cover.png?auto=&bg=transparent&con=3&cs=srgb&dpr=1&fit=clip&fm=png&h=1200&ixlib=php-3.1.0&q=65&usm=15&vib=3&w=1200&s=79575b05cb7a0c3f94e7fde28060a873);
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
