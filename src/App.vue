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

  width: min(80%, 600px);
  margin: 0 auto;
  padding: 2rem;

  box-shadow: 1rem 1rem 0 rgba(255, 255, 255, 0.7);

  & h1 {
    font-size: 3rem;
    font-weight: 700;
    color: #f0f0f0;
  }

  & h2 {
    font-size: 2rem;
  }

  & h3 {
    font-size: 1.8rem;
    color: #f0f0f0;
    font-weight: 500;
  }

  & p {
    font-size: 1.6rem;
    color: #eee;
  }
}
</style>
