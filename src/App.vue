<template>
  <div id="app">  
    <Jobs v-bind:jobs="json"></Jobs>
  </div>
</template> 
<script>
import Jobs from './components/Jobs.vue' 
 
import json from "../data/data.json";

export default {
 name: 'app',
 components: {
    Jobs
  },
  
  data:  function () {
    return {
      msg: 'Welcome to Your Vue.js App',
      json 
    }
  },
  mounted: function() {  
    //console.log(json);
  }
}
</script>

<style lang="scss">
@import url('./assets/scss/app.scss');
</style>
