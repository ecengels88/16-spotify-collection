<template lang="html">
  <div class="panel">
    <div class="panel-heading">The Black Keys</div>
      <div class="results">

      </div>
  </div>
</template>

<script>
import SongItem from '.song-item';

export default {
  components: {
    SongItem,
  },

  created() {
    fetch('https://api.spotify.com/v1/search?query=katy&type=track&offset=0&limit=20')
    .then(r => r.json())
    .then((curr) => {
      this.tracks = curr;
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
