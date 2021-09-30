<template>
    <div id="navBar">
        <div class="left">
            <BreadCrumb :ArticleName="ArticleName"/>
        </div>
        <div v-show="atleastPortraitTablet" class="center">
            <SearchBar @inputFieldFocused="inputFieldFocusedHandler"/>
        </div>
        <div class="right">
            <router-link :to="{
                path: '/'
            }" class="subtitle regular" @click="$emit('Home:clicked')">Home</router-link>
            <HamburgerIcon />
        </div>
    </div>
</template>

<script>
// javascript code
import breakpoints from '@/js/scssBreakpoints';

// Vue3 Components
import SearchBar from '@/components/navbar/SearchBar.vue';
import HamburgerIcon from '@/components/navbar/HamburgerIcon.vue';
import BreadCrumb from '@/components/navbar/BreadCrumb.vue';

export default {
    name: "NavBar",
    components:{
        BreadCrumb,
        SearchBar,
        HamburgerIcon
    },
    computed:{
        atleastPortraitTablet(){
            return window.innerWidth >= parseInt(breakpoints.forTabletPortraitUp.breakpoint);
        }
    },
    props:{
        ArticleName:{
            type: String,
            default: "Article Name"
        }
    },
    methods:{
        inputFieldFocusedHandler(focused){
            let center = this.$el.querySelector('.center')
            if(center === null) return; //no need for this to work in mobile phone

            if(focused === true){
                if(window.innerWidth >= parseInt(breakpoints.forDesktopUp.breakpoint))
                    center.style.flexBasis = "60%";    
                else
                    center.style.flexBasis = "40%";
            }
            else{
                if(window.innerWidth >= parseInt(breakpoints.forDesktopUp.breakpoint))
                    center.style.flexBasis = "50%";    
                else
                    center.style.flexBasis = "30%";
            }
        }
    }
}
</script>

<style lang="scss" scoped>
@use '../../assets/scss/setting' as *;

#navBar{
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: var(--spacing-normal);

    background-color: map-get($dark,"darker");
    padding: var(--spacing-normal);
}

.center{
    transition: flex-basis ease-in-out 0.5s;
    flex: 0 0 30%;

    @include for-desktop-up{
        flex: 0 0 50%;
    }

}
.right{
    display: flex;
    align-items: center;
    justify-content: flex-end;
    gap: var(--spacing-large);
}
</style>