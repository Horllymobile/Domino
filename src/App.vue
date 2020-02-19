<template>
  <div>
    <comp-header/>
    <div>
      <comp-featured/>
      <comp-menu/>
    </div>
    <comp-footer/>
  </div>
</template>
<script>

import compHeader from './components/Header_Footer/Header.vue';
import compFooter from './components/Header_Footer/Footer.vue';
import compFeatured from './components/Featured/index.vue';
import compMenu from './components/Menu/index.vue';
export default {

  data(){
    return{

    }
  },
  components:{
    compHeader,
    compFooter,
    compFeatured,
    compMenu
  }
  
}
</script>
<style >
  @import './assets/style.css';
</style>