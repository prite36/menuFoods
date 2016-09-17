<template>
  <div id="app">
    <foods :foods="foods" :up-vote="upVote" :delete-food="deleteFood"></foods>
    <add-food :add-food="addFood"></add-food>
  </div>
</template>

<script>
import Foods from './components/Foods'
import AddFood from './components/AddFood'
export default {
  components: {
    Foods,
    AddFood
  },
  data () {
    return {
      foods: [
        {
          id: Date.now() + Math.random(),
          photo: 'https://lipotwin.files.wordpress.com/2016/01/vkskimtg.jpg',
          name: 'ต้มยำ',
          price: 100,
          vote: 0
        },
        {
          id: Date.now() + Math.random(),
          photo: 'http://www.smeleader.com/wp-content/uploads/2014/03/%E0%B8%99%E0%B8%B4%E0%B8%95%E0%B8%A2%E0%B8%B2%E0%B9%84%E0%B8%81%E0%B9%88%E0%B8%A2%E0%B9%88%E0%B8%B2%E0%B8%87-%E0%B8%AD%E0%B8%B2%E0%B8%8A%E0%B8%B5%E0%B8%9E%E0%B8%A3%E0%B8%B4%E0%B8%A1%E0%B8%97%E0%B8%B2%E0%B8%87-%E0%B8%81%E0%B8%A5%E0%B8%B2%E0%B8%A2%E0%B9%80%E0%B8%9B%E0%B9%87%E0%B8%99%E0%B8%A3%E0%B9%89%E0%B8%B2%E0%B8%99%E0%B8%AD%E0%B8%B2%E0%B8%AB%E0%B8%B2%E0%B8%A3%E0%B8%8A%E0%B8%B7%E0%B9%88%E0%B8%AD%E0%B8%94%E0%B8%B1%E0%B8%87-3.jpg',
          name: 'ไก่ย่าง',
          price: 200,
          vote: 0
        }
      ]
    }
  },
  methods: {
    addFood: function (photo, name, price) {
      var data = {
        id: Date.now() + Math.random(),
        photo: photo,
        name: name,
        price: price,
        vote: 0
      }
      this.foods.push(data)
    },
    upVote: function (id) {
      let index = this.foods.map(item => item.id).indexOf(id)
      this.foods[index].vote ++
    },
    deleteFood: function (id) {
      let index = this.foods.map(item => item.id).indexOf(id)
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
