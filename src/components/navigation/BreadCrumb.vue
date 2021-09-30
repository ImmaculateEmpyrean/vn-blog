<template>
    <div id="BreadCrumb">
        <img :src="require('@/assets/img/logo.svg')" alt="vn-blog logo">
        <h1 class="heading1" id="websiteTitle">Vn Blog</h1>
        <h1 class="heading1">{{ArticleName}}</h1>
    </div>
</template>

<script>
export default {
    name: "BreadCrumb",
    props:{
        ArticleName:{
            type: String,
            default: 'ArticleName'
        }
    }
}
</script>

<style lang="scss" scoped>
@use '../../assets/scss/setting' as *;

#BreadCrumb
{
    display: flex;
    align-items: center;
}

img{
    //the image is always double the size of the hamburger icon on the right side of the screen

    margin: 0 var(--spacing-normal);

    width: 60px;
    height: 60px;

    @include for-tablet-portrait-up{
        width: 100px;
        height: 100px;
    }

    @include for-desktop-up{
        width: 125px;
        height: 125px;
    }
}

#websiteTitle{
    //I want the cutesy divider line between  
    padding:  var(--spacing-small) 0;
    padding-right: var(--spacing-large);
    border-right: 3px solid white;
    margin-right: var(--spacing-large);
}

</style>