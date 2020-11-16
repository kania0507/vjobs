<template>
  <div id="app">  
    <header class="header">
      <div class="header__filters">
        <span class="clear">Clear</span>
      </div>
      </header>
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
@import "/assets/scss/app.scss";
</style>
