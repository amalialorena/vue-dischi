<template>
  <div class="card">
      <div class="img-container">
          <img :src="detail.poster" :alt="detail.title">
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
    width: calc((100% / 5) - 30px);
    margin: 10px 15px;
    padding: 10px;
    color: white;
    background-color: #232c36;
    text-align: center;
    min-width: 100px;
    img {
        width: 100%
    }
    h2 {
        margin-bottom: 10px;
    }
    p {
        color: grey;
        font-size: .8em;
    }
}

</style>