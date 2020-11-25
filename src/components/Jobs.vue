<template>
    <div class="jobs">
     <div class="jobs__row" v-for="(job, index) in activejobs" v-bind:key="index"  >
       <div class="jobs__row__img"><img  v-bind:src= 'job.logo' /></div>
       <div class="jobs__row__h"><h1>{{ job.company }} <span class="jobs__row__h__new" v-if='job.new'>NEW!</span>
        <span class="jobs__row__h__featured" v-if='job.featured'>FEATURED!</span></h1>
        <h2>{{ job.position }}</h2> 
        <p class="jobs__row__h__posted">
          <span>{{ job.postedAt }}</span>  &middot;
          <span>{{ job.contract }}</span>  &middot;
          <span>{{ job.location }}</span>
        </p>
      </div>
      <div class="jobs__row__lang">
        <span class="jobs__row__lang__filter"><a href="#" @click="putFilters(job.role)">{{ job.role}}</a></span>
        <span class="jobs__row__lang__filter"><a href="#" @click="putFilters(job.level)">{{ job.level}}</a></span>
        <span class="jobs__row__lang__filter" v-if="job.languages.length>0" >
          <a v-for="(lang, i) in job.languages" v-bind:key="i" href="#" @click="putFilters(lang)" class="jobs__row__lang__main">{{ lang}}</a>&nbsp;&nbsp;&nbsp;
          </span>
        <span class="jobs__row__lang__filter" v-if="job.tools.length>0" >
          <a v-for="(tool, ind) in job.tools" v-bind:key="ind" href="#" @click="putFilters(tool)" class="jobs__row__lang__tools">{{ tool }}</a>&nbsp;&nbsp;&nbsp;
        </span>
      </div>
      </div>
    </div>
</template> 

<script>

export default {
  name: "Jobs",
  props: ['jobs'],
  data: function () {
    return {    
    };
  },

   computed: {
          activejobs: function() {
            
            if( this.$parent.allFilters.length == 0) return this.jobs;
            
            var activeproduct = [];
            var filters = this.$parent.allFilters;//this.myfilters;  
            
            this.jobs.forEach(function(product) {
                
                function productContainsFilter(filter) {
                    var result = ''; 
                 
                    result = (product.role.indexOf(filter)!= -1 || product.level.indexOf(filter)!= -1 || product.languages.indexOf(filter)!= -1 || product.tools.indexOf(filter)!= -1);
                    return result ;
                }
                
                if(filters.every(productContainsFilter)) {
                    activeproduct.push(product);
                }
            }); 
            return activeproduct;
            }
        },

  methods: {
     putFilters: function(f)
      {
        
        if (!this.$parent.allFilters.includes(f)) this.$parent.allFilters.push(f); 
     }
  },
  mounted: function() {  
      if( this.$parent.allFilters.length == 0) return this.jobs;
    
  } 
};
</script>
