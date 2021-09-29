<template>
    <div id="BreadCrumb">
        <img :src="require('@/assets/img/logo.svg')" alt="vn-blog logo">
        <h1 class="subtitle" id="websiteTitle">Vn Blog</h1>
        <h1 class="subtitle">{{ArticleName}}</h1>
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
@use '../../assets/scss/setting';

#BreadCrumb
{
    display: flex;
    align-items: center;
}

img{
    margin: 0 var(--spacing-normal);
}

#websiteTitle{
    //I want the cutesy divider line between  
    padding:  var(--spacing-small) 0;
    padding-right: var(--spacing-large);
    border-right: 3px solid white;
    margin-right: var(--spacing-large);
}

</style>