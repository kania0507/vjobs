<template>
  <div id="app">  
    <header class="header">
      <div class="header__filters">
        <span v-if="allFilters.length>0" class="header__filters--left" >
          <a v-for="(filter, i) in allFilters" v-bind:key="i" href="#">{{ filter }}[X]</a>
        </span>
        <span class="header__filters--right"><a href="#" @click="removeFilters">Clear</a></span>
      </div>
      </header>
    <Jobs v-bind:jobs="myJson"></Jobs>
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
  
  data: function () {
    return {
      json,
      myJson:[],
      allFilters: [] 
    }
  },
  mounted: function() {  
    //console.log(json);
    if (this.myJson.length==0)
      this.myJson=this.json;
  },
  methods: { 
    removeFilters: function() {
      this.allFilters = [];
      this.myJson=json;
    }
  }
}
</script>

<style lang="scss">
@import "/assets/scss/app.scss";
</style>
