<template>
  <div id="app">
    <show-foods :foods="foods" :up-vote="upVote" :delete-food="deleteFood"></show-foods>
    <add-food :add-food="addFood"></add-food>
  </div>
</template>

<script>
import ShowFoods from './components/ShowFoods'
import AddFood from './components/AddFood'
export default {
  components: {
    ShowFoods,
    AddFood
  },
  data () {
    return {
      foods: [{
        photo: 'https://lipotwin.files.wordpress.com/2016/01/vkskimtg.jpg',
        name: 'ต้มยำ',
        price: 100,
        vote: 0,
        id: 0
      }]
    }
  },
  methods: {
    addFood: function (photo, name, price) {
      var data = {
        photo: photo,
        name: name,
        price: price,
        vote: 0,
        id: this.foods.length
      }
      this.foods.push(data)
    },
    upVote: function (index) {
      console.log(index)
      this.foods[index].vote ++
    },
    deleteFood: function (index) {
      this.foods.splice(index, 1)
    }
  }
}
</script>

<style>
html {
  height: 100%;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}

#app {
  color: #2c3e50;
  margin-top: -100px;
  max-width: 600px;
  font-family: Source Sans Pro, Helvetica, sans-serif;
  text-align: center;
}

#app a {
  color: #42b983;
  text-decoration: none;
}

.logo {
  width: 100px;
  height: 100px
}
</style>
