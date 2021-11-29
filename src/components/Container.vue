<template>
<div class="container">
<div class="select-container">
      <select v-model="selected" id="" > 
          <option disabled value="">Filter by genre</option>
          <option value="Jazz">Jazz</option>
          <option value="Pop">Pop</option>
          <option value="Rock">Rock</option>
          <option value="Metal">Metal</option>
      </select>
      <span class="debug">selected: {{selected}}</span>

    <div id="cards-container">
      <Card
      v-for="disk,i in filterByGenre"
      :key="i"
      :detail = disk
      />
  </div>
    </div>

</div>

</template>

<script>
import Card from '@/components/Card.vue';
import axios from 'axios'

export default {
  name: 'Container',
   components: {
    Card,
   },
data() {
    return {
        apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
        disks: [],
        selected: "",
    }
},

created () {
    this.getDisks()
},

computed: {
//     filteredDisks(){
//         if(this.value === "") {
//             console.log("value",this.value),
//             return this.disks;
//             }
    
//         return this.disks.filter((item) => {
//             console.log(this.value),
//                 return item.genre.includes("value",this.value)
        
//     })
// }
    filterByGenre () {
        if(this.selected === "") {
            return this.disks
        }
        return this.disks.filter((item) => {
            return item.genre.includes(this.selected)
        })
    }
},

methods: {
    getDisks () {
        axios
        .get(this.apiUrl)
        .then((result) => {
            this.disks = result.data.response
        })

    }
}
}

</script>


<!-- -->

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    #cards-container {
        width: 70%;
        margin: 40px auto;
        display: flex;
        flex-wrap: wrap;
    }
    .debug {
        color: white
    }
</style>
