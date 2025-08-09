<template>
  <section class="queue-card" theme="dark">
    <draggable v-model="localSongs" tag="ul" item-key="title" class="song-list" ghost-class="ghost"
      chosen-class="chosen">
      <template #item="{ element }">
        <li class="song-item">
          <div class="drag-handle">⋮⋮</div>
          <img :src="element.cover" :alt="`Album cover of ${element.title}`" />
          <div class="song-details">
            <h3>{{ element.title }}</h3>
            <p>{{ element.artist.join(', ') }} - {{ element.album }} ({{ element.year }})</p>
            <span>{{ element.duration }}</span>
          </div>
        </li>
      </template>
    </draggable>
  </section>
</template>

<script>
import draggable from 'vuedraggable';

export default {
  name: 'QueueCard',
  components: {
    draggable
  },
  props: {
    songs: {
      type: Array,
      required: true
    }
  },
  computed: {
    localSongs: {
      get() {
        return this.songs;
      },
      set(value) {
        this.$emit('update:songs', value);
      }
    }
  }
}
</script>

<style scoped>
.queue-card {
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

.drag-handle {
  color: var(--clr-primary-2);
  font-size: 1.4rem;
  cursor: grab;
  user-select: none;
}

/* You can add background colors to .ghost and .chosen for more effects. */
.ghost {
  opacity: 0;
}

.chosen {
  opacity: 0.7;
}
</style>