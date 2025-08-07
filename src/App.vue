<template>
  <div id="app">
    <div class="login">
      <h1>Log In</h1>
      <p>Some cool subtitle</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
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

.login {
  width: min(80%, 600px);
  margin: 0 auto;
  padding: 2rem;
  background-color: #333;
  box-shadow: 1rem 1rem 0 rgba(255, 255, 255, 0.7);

  & h1 {
    font-size: 3rem;
    font-weight: 700;
    color: #f0f0f0;
  }

  & p {
    font-size: 1.6rem;
    color: #eee;
  }
}
</style>
