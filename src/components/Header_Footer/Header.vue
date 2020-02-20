<template>
    <header>
        <div class="container clear">
            <div class="logo" v-scroll-reveal.reset="{delay:200}">
                <img :src="logoIcon">
            </div>
            <div class="nav" v-scroll-reveal.reset="{delay:250}">
                <img :src="menuIcon" alt="Menu Icon" @click="showSidePanel = !showSidePanel">
            </div> 
            <md-drawer
                class="side-drawer"
                :md-right="true"
                :md-active.sync="showSidePanel"
            />
        </div> 
    </header>
</template>

<script>
    import Logo from '../../assets/images/logo.png';
    import Menu from '../../assets/images/menu.png';
export default {
    data(){
        return {
            logoIcon:Logo,
            menuIcon:Menu,
            showSidePanel:false,
        }
    },
    methods:{
        
    }
}
</script>

