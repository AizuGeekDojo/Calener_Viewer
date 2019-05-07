<template>
  <div class="contents">
    <iframe
      class="movie"
      type="text/html"
      width="720"
      height="405"
      src="https://www.youtube.com/embed/ODhsndH_6os?autoplay=1&loop=1&playlist=ODhsndH_6os"
      frameborder="0"
      allowfullscreen
    ></iframe>
  </div>
</template>

<script>
export default {
  data() {
    return {
      videoId: "ODhsndH_6os",
      playerVars: {
        autoplay: 1
      }
    };
  },
  methods: {
    playing() {}
  }
};
</script>
<style scoped>
.contents {
  width: 100%;
  height: 100%;
}

.movie {
  width: 100%;
  height: 100%;
}
</style>
