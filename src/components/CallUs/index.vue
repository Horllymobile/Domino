<template>
    <div class="call_us_container">

        <div class="container">

            <div class="first" v-scroll-reveal.reset="{delay:300,scale:2 }">
                <h1>Hungry ?</h1>
            </div>

            <div class="second" v-scroll-reveal.reset="{delay:300,afterReveal:()=>{
                    secondAnim = true
                }}">
                <div v-if="secondAnim">
                    <comp-anim/>
                </div>
            </div>

            <div class="third" v-scroll-reveal.reset="{delay:350,scale:2}">
                <span>Give us a call <span style="color:white"> 6666-3399</span></span>
            </div>
        </div>
        
    </div>
</template>

<script>
import compAnim from './Anim.vue';
export default {
    data(){
        return {
            secondAnim:false,
        }
    },
    components:{
        compAnim
    }
}
</script>