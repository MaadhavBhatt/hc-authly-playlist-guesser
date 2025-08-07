<template>
  <div class="login">
    <h1>Guess the playlist to enter</h1>
    <p>Some cool subtitle</p>
  </div>
</template>

<script>
export default {
  name: 'LoginCard'
}
</script>

<style scoped>
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