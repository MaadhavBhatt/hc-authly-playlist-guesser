<template>
  <section class="login" :theme="unlocked ? 'dark' : 'light'">
    <h1>Guess the playlist to enter</h1>
    <p class="subtitle">Some cool subtitle</p>
  </section>
</template>

<script>
export default {
  name: 'LoginCard',
  props: {
    unlocked: {
      type: Boolean,
      default: false
    }
  }
}
</script>