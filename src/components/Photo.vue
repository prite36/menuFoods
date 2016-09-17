<template>
  <img :src="photo" alt="" />
</template>

<script>
export default {
  props: ['photo'],
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
img {
  width: 200px;
}
</style>
