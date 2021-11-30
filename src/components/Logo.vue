<template>
  <nav>
      <div class="logo">
           <i class="fab fa-spotify"></i>    
      </div>
      <div class="select-container">
          <select v-model="selected" id="" v-on:change="$emit('option', selected)"> 
              <option disabled value="">Filter by genre</option>
              <option value="Jazz">Jazz</option>
              <option value="Pop">Pop</option>
              <option value="Rock">Rock</option>
              <option value="Metal">Metal</option>
          </select>
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
        display: flex;
        justify-content: space-between;
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
