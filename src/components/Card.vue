<template>
  <div class="card">
      <div class="img-container">
          <img src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
      </div>
      <h2>new jersey</h2>
      <p>bon jovi</p>
      <p>1988</p>
   
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    msg: String
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