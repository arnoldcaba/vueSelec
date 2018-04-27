<template>
  <div>
    <v-select v-model="selected" :options="['foo','bar']"></v-select>
  </div>
  
</template>

<script>
export default {
  name: 'Select',
  data () {
    return {
      selected: null
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>