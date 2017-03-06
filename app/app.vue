<template lang="html">
  <div class="section">
    <div class="container">
      <div class="panel">
        <!-- <form action=""> -->
          <p class="panel-heading">

            <input class="input" placeholder="Search For Your Band" v-on:keydown.enter="search(searchTerm)" v-model="searchTerm">
          </p>
        <!-- </form> -->
          <div class="results">
      <song-item  v-for="current in tracks" v-bind:track="current"></song-item>
          </div>
      </div>
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
    this.search('Hugh Laurie');
  },

  data() {
    return {
      tracks: [],
      searchTerm: '',
    };
  },

  methods: {
    search(bandName) {
      fetch(`https://api.spotify.com/v1/search?query=${bandName}&type=track&offset=0&limit=20`)
      .then(r => r.json())
      .then((curr) => {
        this.tracks = curr.tracks.items;
      });
    }
  },
};
</script>
