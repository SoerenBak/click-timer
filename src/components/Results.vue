<template>
  <div class="results">
    <p>score {{ score }} ms</p>
    <p>{{ rank }}</p>
  </div>
</template>

<script>
export default {
    props: ['score'], 
    data() {
      return {
        rank: null
      }
    },
    mounted() {
      if(this.score < 250) {
        this.rank = "Very fast"
      } else if (this.score < 400 ) {
        this.rank = "Normal"
      } else {
        this.rank = "Slow....try again"
      }
    }
}
</script>

<style>

</style>