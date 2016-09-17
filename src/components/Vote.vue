<template>
  <button @click="upVote(index)">Vote {{vote}}</button>
</template>

<script>
export default {
  props: ['vote', 'upVote', 'index'],
  data () {
    return {
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  color: #42b983;
}
</style>
