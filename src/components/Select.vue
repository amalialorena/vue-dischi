<template>
<div class="select-container">
      <select v-model="selected" id="" v-on:change="$emit('option', selected)"> 
          <option disabled value="">Filter by genre</option>
          <option value="Jazz">Jazz</option>
          <option value="Pop">Pop</option>
          <option value="Rock">Rock</option>
          <option value="Metal">Metal</option>
      </select>
      <span class="debug">selected: {{selected}}</span>
</div>
</template>

<script>
export default {
  name: 'Select',
  
 data() {
    return {
        selected: "",
    }
},
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .debug {
        color: white
    }

</style>