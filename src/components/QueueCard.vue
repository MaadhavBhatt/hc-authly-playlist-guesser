<template>
  <section class="queue-card">
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
  background-color: #444;
  color: #fff;

  & ul {
    list-style: none;
    padding: 0;

    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  & li {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 1rem;

    cursor: pointer;
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