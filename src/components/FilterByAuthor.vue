<template>
  <div class="select-container">
      <!-- <select v-model="selectAuthor" id="">
          <option value="">Filter by Author</option>
          <option value="" v-for="object, i in detail" :key="i">{{object.author}}</option> -->
      <!-- </select> -->
      
    <!-- <span>{{author}}</span> -->
  </div>
</template>

<script>
export default {
  name: "FilterByAuthor",
//   props: {
//       detail : Object
//   },

  data () {
      return {

      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .select-container {
        color: white;
    }

</style>