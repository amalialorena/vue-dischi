<template>
  <div class="container">
    <!-- <Select @option="filterByGenre"/> -->
    <!-- <FilterByAuthor :detail='disks'  /> -->
    <div id="cards-container">
      <Card v-for="(disk, i) in filtered" :key="i" :detail='disk' />
    </div>
  </div>
</template>

<script>
import Card from "@/components/Card.vue";
// import Select from "@/components/Select.vue";
import axios from "axios";

export default {
  name: "Container",
  components: {
    Card,
    // Select, 
  },
  props: {
    info: String
  },

  data() {
    return {
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      disks: [],
    };
  },

  created() {
    this.getDisks();
  },

  computed: {
    filtered() {
      let filteredArray = this.disks;
      let element = this.info;
      console.log(element)
      if (element === "") {
        return filteredArray;
      }
      
      filteredArray = filteredArray.filter((item) => {
        return item.genre === element;
      });

      return filteredArray;
    },
  },

  methods: {
    getDisks() {
      axios.get(this.apiUrl).then((result) => {
        this.disks = result.data.response;
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
#cards-container {
  width: 70%;
  margin: 40px auto;
  display: flex;
  flex-wrap: wrap;
}
.debug {
  color: white;
}
</style>
