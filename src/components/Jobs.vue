<template>
    <div class="jobs"> {{ message }}
        <div  v-for="data in jobs"  v-bind:key="data">{{data}}</div>
    </div>
</template>

// Importing array from local JSON file "@/assets/data.json";
import json from "@/assets/data.json";

export default {
  name: "Jobs",
  data: 
    function() {
    return {
      jobs: json, // passing array data into Vue
      menu:[],
      message: '',
    };
  },
  methods: {
     GetMenu:function(){
      $.get({
        url: '../assets/data.json',
        success:function(res) {
          this.menu = res.menu;
        }.bind(this)
      })
    }
  },

  mounted: function() { 
    this.jobs: json;
     console.log(this.jobs);
     json.forEach(jobs => { console.log(jobs.company); });
  },
  created:function(){
    this.GetMenu();
    console.log(this.menu);
  }
};