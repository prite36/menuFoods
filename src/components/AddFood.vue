<template>
  Img: <input v-model="photo"><br>
  Name: <input v-model="name"><br>
  Price: <input v-model="price"><br>
  <button @click="addFood(photo, name, price)">Add</button>
</template>

<script>
export default {
  props: ['addFood'],
  data () {
    return {
      photo: '',
      name: '',
      price: ''
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
