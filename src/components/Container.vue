<template>
  <div id="cards-container">
      <Card
      v-for="disk,i in disks"
      :key="i"
      />
  </div>
</template>

<script>
import Card from '@/components/Card.vue';
// import axios from 'axios'

export default {
  name: 'CardsContainer',
   components: {
    Card
  },

data () {
    return {
        // apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
        disks: []
    }
},

// created () {
//     this.getDisks()
// },

// methods: {
//     getDisks () {
//         axios
//         .get(this.apiUrl)
//         .then((result) => {
//             this.disks = result
//             console.log(result)
//         })

//     }
// }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    #container {
        width: 70%;
        margin: 40px auto;
    }
</style>
