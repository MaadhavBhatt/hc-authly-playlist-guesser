<template>
  <div id="app">
    <LoginCard />
  </div>
</template>

<script>
import LoginCard from './components/LoginCard.vue'

export default {
  name: 'App',
  components: { LoginCard },
}
</script>

<style>
:root {
  font-size: 10px;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  width: 100%;
  min-height: 100vh;
  display: grid;
  place-items: center;
  background-color: #8c91a5;
}
</style>
