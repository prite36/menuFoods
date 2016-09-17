<template>
  <div class="">
    <photo :photo="food.photo"></photo>
    <h1>{{ index }}</h1>
    <info :name="food.name" :price="food.price"></info>
    <vote :vote="food.vote" :up-vote="upVote" :index="index"></vote>
  </div>
</template>

<script>
import Photo from './Photo'
import Info from './Info'
import Vote from './Vote'
export default {
  props: ['food', 'upVote', 'index'],
  data () {
    return {
    }
  },
  components: {
    Photo,
    Info,
    Vote
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  color: #42b983;
}
</style>
