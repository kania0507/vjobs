<template>
    <div class="jobs">
     <div class="jobs__row" v-for="(job, index) in jobs" v-bind:key="index">
       <div class="jobs__row__img"><img class="jobs__row__img" v-bind:src= 'job.logo' /></div>
       <div class="jobs__row__h"><h1 class="jobs__row__h">{{ job.company }} <span class="jobs__row__h__new" v-if='job.new'>NEW!</span>
        <span class="jobs__row__h__featured" v-if='job.featured'>FEATURED!</span></h1>
        <h2>{{ job.position }}</h2> 
        <p>
          <span>{{ job.postedAt }}</span>
          <span>{{ job.contract }}</span>
          <span>{{ job.location }}</span>
        </p>
      </div>
      <div class="jobs__row__lang">
        <p>{{ job.languages}}</p>
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
  methods: {
   
  },
  mounted: function() { 
  },
  created:function(){ 
  }
};
</script>