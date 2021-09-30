<template>
   <div id="app">
        <Navigation />        
   </div>
</template>

<script>
import Navigation from './components/navigation/Navigation.vue';

export default {
    name: "App",
    components:{
        Navigation
    }
}
</script>

<style lang="scss">
    @use './assets/scss/setting' as *;

    #app{
        height: 1000vw;
    }
</style>