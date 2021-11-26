<template>
  <nav>
      <div class="logo">
           <i class="fab fa-spotify"></i>
      </div>
     
  </nav>
</template>

<script>

export default {
  name: 'Logo',
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    nav {
        height: 70px;
        background-color:#222c36;
        .logo {
            height: 100%;
            color: #25d24d;
            font-size: 50px;
            i {
              margin-left: 10px;
              vertical-align: middle;
            } 
            img {
            height: 100%;
            border-radius: 50%;
            } 
        }
    }
</style>
