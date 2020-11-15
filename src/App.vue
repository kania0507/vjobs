<template>
  <div id="app"> 
    <h1>{{ msg }}</h1> 
  </div>
</template>

<script>
import Jobs from './components/Jobs.vue'
export default {
  name: 'app',
 components: {
    Jobs
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<style lang="scss">

</style>
