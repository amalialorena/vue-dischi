<template>
<div class="container">
 <!-- <div class="select-container">
 <select v-model="selected" id="" > 
          <option disabled value="">Filter by genre</option>
          <option value="Jazz">Jazz</option>
          <option value="Pop">Pop</option>
          <option value="Rock">Rock</option>
          <option value="Metal">Metal</option>
      </select>
</div> -->
      <Select @option="filterByGenre"/>
      <!-- <span class="debug">selected: {{selected}}</span> -->

    <div id="cards-container">
      <Card
      v-for="disk,i in filtered"
      :key="i"
      :detail = disk
      />
  </div>
</div>



</template>

<script>
import Card from '@/components/Card.vue';
import Select from '@/components/Select.vue';
import axios from 'axios'

export default {
  name: 'Container',
   components: {
    Card,
    Select
   },
data() {
    return {
        apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
        disks: [],
        selected: ""
    }
},

created () {
    this.getDisks()
},

computed: {
    filtered () {
        let filtered = this.disks;
        let element  = this.selected;
        if(element === "") {
            return filtered
        }
        filtered = filtered.filter((item) => {
            return item.genre === this.selected
        });
        return filtered;
    }
},

methods: {
    getDisks () {
        axios
        .get(this.apiUrl)
        .then((result) => {
            this.disks = result.data.response

        })
    
    },

    filterByGenre(event) {
        this.selected = event;
    },
    
//     filterByGenre (element) {
//         console.log(element)
//         this.selected = element
//         if(this.selected === "") {
//             // console.log(element)
//             // console.log(this.disks)
//             return this.disks
//         }
        
//         return this.disks.filter((item) => {
//             // console.log(item.genre)
//             //  console.log(this.disks)
//             return item.genre == this.selected
//         })
//     }
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
