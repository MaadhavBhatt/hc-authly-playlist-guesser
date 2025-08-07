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

  --width: min(80%, 600px);
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  width: 100%;
  min-height: 100vh;
  background-color: #8c91a5;

  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 4rem;
}

section {
  display: flex;
  flex-direction: column;
  align-items: start;
  justify-content: center;
  gap: 1rem;

  margin: 0 auto;
}
</style>
