<template>
    <div id="navigation">
        <NavBar @HamburgerIcon:clicked="testHandlerMainMenu"/>
        <SideMenu class="hidden"/>
    </div>
</template>

<script>
import NavBar from '@/components/navigation/NavBar.vue';
import SideMenu from '@/components/navigation/SideMenu.vue';

export default {
    name:'Navigation',
    components:{
        NavBar,
        SideMenu
    },
    mounted(){
        let navigationComponent = document.getElementById('navigation');
        navigationComponent.style.height = `${window.innerHeight}px`;
    },
    methods:{
        testHandlerMainMenu(){
            let SideMenu = this.$el.querySelector('#SideMenu');
            SideMenu.classList.toggle('hidden');
            console.log('test')
        }
    }
}
</script>

<style lang="scss" scoped>
@use '../../assets/scss/setting' as *;

#navigation{
    display: flex;
    position: fixed;
    width: 100%;

    flex-direction: column;
}

#SideMenu{
    transition: transform ease-in-out 0.5s;
    flex: 1 1 100%;
    
    width: 100%;
    @include for-tablet-portrait-up{
        align-self: flex-end;
        width: 50%;
    }
    @include for-desktop-up{
        width: 20%;
    }

    &.hidden{
        transform: translateY(100vh);
        @include for-tablet-portrait-up{
            transform: translateX(50vw);
        }
        @include for-desktop-up{
            transform: translateX(20vw);
        }
    }
}
</style>