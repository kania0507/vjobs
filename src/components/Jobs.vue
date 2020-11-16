<template>
    <div class="jobs"> Jobs-component 
     <div v-for="(job, index) in jobs" v-bind:key="index">
      {{ job.company }} 
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