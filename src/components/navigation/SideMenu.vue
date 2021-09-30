<template>
    <div id="SideMenu">
        <h1 class="heading1">Menu</h1>    
        <div class="sections">
            <Section title="Site Navigation">
                <template v-slot:links>
                    <li><router-link :to="{path: '/'      }">Home   </router-link></li>
                    <li><router-link :to="{path: '/Search'}">Search </router-link></li>
                    <li><router-link :to="{path: '/About' }">About  </router-link></li>
                </template>
            </Section>

            <Section title="Social Media">
                <template v-slot:links>
                    <li><a href="#">Instagram</a></li>
                    <li><a href="#">Twitter</a></li>
                    <li><a href="#">Facebook</a></li>
                </template>
            </Section>

            <Section title="Resources">
                <template v-slot:links>
                    <li><a href="#">Advertising</a></li>
                    <li><a href="#">Terms Of Use</a></li>
                    <li><a href="#">Cookie Policy</a></li>
                    <li><a href="#">Privacy</a></li>
                </template>
            </Section>

            <Section title="Help">
                <template v-slot:links>
                    <li><a href="#">Contact Me</a></li>
                    <li><a href="#">My Website</a></li>
                    <li><a href="#">Send An Email</a></li>
                    <li><a href="#">Discord</a></li>
                </template>
            </Section>
        </div>
    </div>
</template>

<script>
import Section from '@/components/navigation/Section.vue';

export default {
    name: 'SideMenu',
    components:{
        Section
    },
   
}
</script>

<style lang="scss" scoped>
@use '../../assets/scss/setting' as *;

#SideMenu{
    background-color: rgba($color: #000000, $alpha: 0.5);
}
.sections{
    display: flex;
    flex-direction: column;
    gap: var(--spacing-large);
}

.heading1{
    margin: var(--spacing-large) 0;
}

li a{ @extend .heading3; }
</style>