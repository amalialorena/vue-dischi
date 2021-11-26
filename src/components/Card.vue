<template>
  <div class="card">
      <div class="img-container">
          <img :src="detail.poster" alt="">
      </div>
      <h2>{{detail.title}}</h2>
      <p>{{detail.author}}</p>
      <p>{{detail.year}}</p>
   
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    detail: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.card {
    width: 150px;
    padding: 10px;
    color: white;
    background-color: black;
    border: 1px solid white;
    img {
        width: 100%
    }
}

</style>