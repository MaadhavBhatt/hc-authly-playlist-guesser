<template>
  <section class="queue-card" theme="dark">
    <ul>
      <li v-for="(song, index) in songs" :key="index">
        <img :src="song.cover" alt="Album cover" />
        <div class="song-details">
          <h3>{{ song.title }}</h3>
          <p>{{ song.artist.join(', ') }} - {{ song.album }} ({{ song.year }})</p>
          <span>{{ song.duration }}</span>
        </div>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  name: 'QueueCard',
  props: {
    songs: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
.queue-card {
  background-color: var(--clr-black);

  /* Override default padding from section in App.vue */
  padding: 2rem 2rem;

  & ul {
    list-style: none;
    padding: 0;
    width: 100%;
  }

  & li {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 1rem;

    padding: 1rem 1rem;

    cursor: pointer;
    transition: background-color 0.2s;
  }

  & li:hover,
  & li:focus {
    background-color: #444;
    transition: background-color 0.2s;
  }

  & img {
    width: 50px;
    aspect-ratio: 1;
    border-radius: 0.25rem;
  }

  & .song-details {
    flex: 1;
  }

  & .song-details h3 {
    margin: 0;
    font-size: 1.6rem;
  }
}
</style>