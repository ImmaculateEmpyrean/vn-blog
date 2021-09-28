<template>
    <div id="navBar">
        <div class="left">
            <img :src="require('@/assets/img/logo.svg')" alt="vn-blog logo">
            <h1 class="subtitle">Vn Blog</h1>
            <h1 class="subtitle">{{ArticleName}}</h1>
        </div>
        <div v-show="atleastPortraitTablet" class="center">
            <SearchBar />
        </div>
        <div class="right">

        </div>
    </div>
</template>

<script>
// javascript code
import breakpoints from '@/js/scssBreakpoints';

// Vue3 Components
import SearchBar from './SearchBar.vue';

export default {
    name: "NavBar",
    components:{
        SearchBar
    },
    computed:{
        atleastPortraitTablet(){
            return window.innerWidth > parseInt(breakpoints.forTabletPortraitUp.breakpoint);
        }
    },
    props:{
        ArticleName:{
            type: String,
            default: "Article Name"
        }
    }
}
</script>

<style lang="scss" scoped>
@use '../../assets/scss/setting' as *;

</style>