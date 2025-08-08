<template>
  <div id="app">
    <LoginCard />
    <QueueCard :songs="songs" />
  </div>
</template>

<script>
import LoginCard from './components/LoginCard.vue'
import QueueCard from './components/QueueCard.vue'

export default {
  name: 'App',
  components: { LoginCard, QueueCard },
  data() {
    return {
      songs: [
        {
          title: 'Shake It Off',
          artist: ['Taylor Swift'],
          album: '1989',
          year: 2014,
          genre: 'Pop',
          duration: '3:39',
          cover: 'https://placehold.co/50'
        },
        {
          title: 'Run (feat. Ed Sheeran)',
          artist: ['Taylor Swift', 'Ed Sheeran'],
          album: 'Red',
          year: 2021,
          genre: 'Pop',
          duration: '3:42',
          cover: 'https://placehold.co/50'
        },
        {
          title: 'Blank Space',
          artist: ['Taylor Swift'],
          album: '1989',
          year: 2014,
          genre: 'Pop',
          duration: '3:51',
          cover: 'https://placehold.co/50'
        }
      ]
    }
  }
}
</script>

<style>
:root {
  font-size: 10px;

  --clr-black: rgb(51, 51, 51);
  --clr-primary-1: rgba(0, 61, 77, 0.3);
  --clr-primary-2: hsla(297, 50%, 80%, 1);
  --clr-accent: rgba(136, 63, 89, 0.53);
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  width: 100%;
  min-height: 100vh;
  background-color: #222;

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
  padding: 2rem 3rem;

  box-shadow: var(--box-shadow, initial);

  &[theme="light"] {
    --clr-h1: #222;
    --clr-h2: #222;
    --clr-h3: #222;
    --clr-p: #222;
    --box-shadow: 1rem 1rem 0 rgba(255, 255, 255, 0.4);
  }

  &[theme="dark"] {
    --clr-h1: #f0f0f0;
    --clr-h2: #f0f0f0;
    --clr-h3: #f0f0f0;
    --clr-p: #eee;
    --box-shadow: 1rem 1rem 0 rgba(255, 255, 255, 0.7);
  }

  & h1 {
    font-size: 3rem;
    font-weight: 700;
    color: var(--clr-h1);
  }

  & h2 {
    font-size: 2rem;
    color: var(--clr-h2);
  }

  & h3 {
    font-size: 1.8rem;
    font-weight: 500;
    color: var(--clr-h3);
  }

  & p,
  & span {
    font-size: 1.2rem;
    color: var(--clr-p);
  }

  & p.subtitle {
    font-size: 1.6rem;
  }
}
</style>
