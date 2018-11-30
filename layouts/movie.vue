<template>
  <div class="movie-layout">
    <movie-header/>
    <nuxt/>
  </div>
</template>
<script>
import MovieHeader from '~/components/MovieHeader'
export default {
  components: {
    MovieHeader
  }
}
</script>
<style scoped>
.movie-layout {
  padding-top: 60px;
}
</style>


