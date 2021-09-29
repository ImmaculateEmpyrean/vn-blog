<template>
   <div id="app">
        <NavBar />        
   </div>
</template>

<script>
import NavBar from './components/navbar/NavBar.vue';

export default {
    name: "App",
    components:{
        NavBar
    }
}
</script>

<style lang="scss">
    @use './assets/scss/setting' as *;
</style>