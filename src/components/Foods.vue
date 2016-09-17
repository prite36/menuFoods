<template>
  <div v-for="food in foods | orderBy 'vote'-1">
    <card :food="food" :up-vote="upVote" :index="food.id" :delete-food="deleteFood"></card>
  </div>

</template>

<script>
import Card from './Card'

export default {
  props: ['foods', 'upVote', 'deleteFood'],
  data () {
    return {
    }
  },
  components: {
    Card
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  color: #42b983;
}
</style>
