<template>
  <div id="app">
    <router-link to="newcomponent">newcomponent</router-link>
  </div> 
</template>

<script>
import axios from 'axios'
export default {
  name: 'HelloWorld',
  data () {
    return {
      options: []
    }
  },
  methods: {
    onSearch(search, loading) {
      loading(true);
      //this.search(loading, search, this);
      axios.get('https://randomuser.me/api/?results=50')
        .then((response) => {
          console.log(response.data.results)
          this.options = response.data.results
          //response.json().then(json => (this.options = json.items))
          loading(false)
        })
    },
    /*search ((loading, search, vm) => {
      fetch(
        `https://api.github.com/search/repositories?q=${escape(search)}`
      ).then(res => {
        res.json().then(json => (vm.options = json.items));
        loading(false);
      });
    }, 350)*/
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
