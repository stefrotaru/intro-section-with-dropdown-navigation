<template>
  <div class="app">
    <NavBar/>
    <MainContent/>
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue';
import MainContent from './components/MainContent/MainContent.vue';

export default {
  name: 'App',
  components: {
    NavBar,
    MainContent,
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Epilogue:wght@500;700&display=swap');

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  font-family: 'Epilogue', sans-serif;
}

body {}

.app {
  display: flex;
  flex-direction: column;
}
.nav-bar {}
</style>
