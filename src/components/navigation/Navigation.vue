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
    #navigation{
        display: flex;
        position: fixed;
        width: 100%;

        flex-direction: column;
    }

    #SideMenu{
        flex: 1 1 100%;
        width: 20%;

        align-self: flex-end;

        border: 1px solid red;

        &.hidden{
            transform: translateX(20vw);
        }
    }
</style>