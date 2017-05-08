<template lang="html">
  <div class="panel-block is-marginless media">
      <figure class="track__frame media-left">
        <img v-bind:src="track.album.images[0].url">
      </figure>

        <div class="media-content is-fullwidth">
          <p class="track__artist"><strong>{{track.artists[0].name}}</strong></p>
          <p class="track__name">{{track.name}}</p>
        </div>

      <div class="media-right">
        <a v-bind:href="track.external_urls.spotify"><span class="icon is-large fa fa-spotify"></span></a>
      </div>
  </div>
</template>

<script>
export default {

  props: ['track'],

  data() {
    return {
    };
  },

  methods: {

  },
};
</script>
