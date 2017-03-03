<template lang="html">
  <div class="panel">
    <div class="panel-heading">The Black Keys</div>
      <div class="results">
<song-item  v-for="current in tracks" v-bind:track="current"></song-item>
      </div>
  </div>
</template>

<script>
import SongItem from './song-item.vue';

export default {
  components: {
    SongItem,
  },

  created() {
    fetch('https://api.spotify.com/v1/search?query=black+keys&type=track&offset=0&limit=20')
    .then(r => r.json())
    .then((curr) => {
      this.tracks = curr.tracks.items;
    });
  },

  data() {
    return {
      tracks: [],
    };
  },

  methods: {

  },
};
</script>
