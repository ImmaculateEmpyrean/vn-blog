<template>
    <div class="SideMenuSection">
        <h2 class="heading2">{{title}}</h2>
        <ul>
            <slot name="links"></slot>
        </ul>
    </div>
</template>

<script>
export default {
    name: "SideMenuSection",
    props:{
        title:{
            type:String,
            default: "NavLinks"
        }
    }
}
</script>

<style lang="scss" scoped>
@use '../../assets/scss/setting' as *;

.SideMenuSection{
    margin: var(--spacing-large);

    .heading2{
        margin-bottom: var(--spacing-small);
        text-align: center;
        
        @include for-desktop-up{ text-align: left; }
    }
}
</style>