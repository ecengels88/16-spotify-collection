<template lang="html">
  <div class="panel-block">
    <span class="media">
      <figure class="track__frame media-left">
        <img src="http://bulma.io/images/placeholders/128x128.png">
      </figure>
      <div class="panel-block">
        <div class="media-content is-fullwidth">
          <p class="track__artist"><strong>Katy Perry</strong></p>
          <p class="track__name">Rise</p>
        </div>
      </div>
      <div class="media-right">
        <a href="#"><span class="icon is-large fa fa-spotify"></span></a>
      </div>
    </span>
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
