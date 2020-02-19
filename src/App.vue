<template>
  <div>
    <compHeader/>
    <div>
      content
    </div>
    <compFooter/>
  </div>
</template>
<script>

import compHeader from './components/Header_Footer/Header.vue'
import compFooter from './components/Header_Footer/Footer.vue'
export default {

  data(){
    return{

    }
  },
  components:{
    compHeader,
    compFooter
  }
  
}
</script>
<style >
  @import './assets/style.css';
</style>