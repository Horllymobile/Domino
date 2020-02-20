<template>
  <div>
    <comp-header/>
    <div>
      <comp-featured/>
      <comp-menu/>
      <comp-call-us/>
      <comp-newsletter/>
    </div>
    <comp-footer/>
  </div>
</template>
<script>

import compHeader from './components/Header_Footer/Header.vue';
import compFooter from './components/Header_Footer/Footer.vue';
import compFeatured from './components/Featured/index.vue';
import compMenu from './components/Menu/index.vue';
import compCallUs from './components/CallUs/index';
import compNewsletter from './components/Newsletter/index.vue';

export default {

  data(){
    return{

    }
  },
  components:{
    compHeader,
    compFooter,
    compFeatured,
    compMenu,
    compCallUs,
    compNewsletter
  }
  
}
</script>
<style >
  @import './assets/style.css';
</style>