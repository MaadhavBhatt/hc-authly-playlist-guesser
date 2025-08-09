<template>
  <div id="app" :class="{ unlocked }">
    <LoginCard :unlocked="unlocked" />
    <QueueCard :songs="songs" @update:songs="updateSongs" />
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
          id: 1,
          title: 'Shake It Off',
          artist: ['Taylor Swift'],
          album: '1989',
          year: 2014,
          genre: 'Pop',
          duration: '3:39',
          cover: 'https://placehold.co/50'
        },
        {
          id: 2,
          title: 'Run (feat. Ed Sheeran)',
          artist: ['Taylor Swift', 'Ed Sheeran'],
          album: 'Red',
          year: 2021,
          genre: 'Pop',
          duration: '3:42',
          cover: 'https://placehold.co/50'
        },
        {
          id: 3,
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
  },
  computed: {
    unlocked() {
      let previousId = -1;
      return !this.songs.some(element => {
        if (element.id <= previousId) {
          return true; // Found an out-of-order song
        }
        previousId = element.id;
        console.log('Current song ID:', element.id);
        return false;
      });
    }
  },
  methods: {
    updateSongs(newSongs) {
      this.songs = newSongs;
    }
  }
}
</script>

<style>
:root {
  font-size: 10px;

  /* Higher numbers correspond to brighter shades */
  --clr-black-1: #222;
  --clr-black-2: #333;
  --clr-white-1: #eee;
  --clr-white-2: #f0f0f0;
  --clr-primary-1: hsla(192, 100%, 15%, 0.3);
  --clr-primary-2: hsla(297, 50%, 90%, 1);
  --clr-accent: hsla(339, 37%, 60%, 0.9);
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  width: 100%;
  min-height: 100vh;

  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 4rem;

  background: linear-gradient(to bottom, #111, #333);

  &.unlocked {
    background: linear-gradient(to bottom, var(--clr-accent), var(--clr-primary-2));
  }
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

  background-color: var(--bg-clr, var(--clr-black-1));
  box-shadow: var(--box-shadow, initial);

  &[theme="light"] {
    --clr-h1: var(--clr-black-1);
    --clr-h2: var(--clr-black-1);
    --clr-h3: var(--clr-black-1);
    --clr-p: var(--clr-black-1);
    --bg-clr: var(--clr-primary-2);
    --box-shadow: 1rem 1rem 0 rgba(255, 255, 255, 0.4);
  }

  &[theme="dark"] {
    --clr-h1: var(--clr-white-2);
    --clr-h2: var(--clr-white-2);
    --clr-h3: var(--clr-white-2);
    --clr-p: var(--clr-white-1);
    --bg-clr: var(--clr-black-2);
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
