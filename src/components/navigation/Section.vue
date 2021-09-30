<template>
    <h2>{{title}}</h2>
    <ul>
        <slot name="links"></slot>
    </ul>
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
</style>