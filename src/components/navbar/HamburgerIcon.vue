<template>
    <div id="hamburgerIcon">
        <svg width="48" height="47" viewBox="0 0 48 47" fill="none" xmlns="http://www.w3.org/2000/svg" class="hamburger-graphic"
        @click="$emit('HamburgerIcon:clicked')"
        >
            <path d="M48 46.0156H0V38.3464H48V46.0156ZM48 26.8424H0V19.1732H48V26.8424ZM48 7.66927H0V0H48V7.66927Z"/>
        </svg>
    </div>
</template>

<script>
export default {
    name: 'HamburgerIcon'
}
</script>

<style lang="scss" scoped>
@use '../../assets/scss/setting' as *;

.hamburger-graphic{
    fill: $light;
    cursor: pointer;

    //the size of the hamburger-graphic is half of that of the logo-image on the right side of the nav-bar

    width: 30px;
    height: 30px;

    @include for-tablet-portrait-up{
        width: 50px;
        height: 50px;
    }

    @include for-desktop-up{
        width: 62.5px;
        height: 62.5px;
    }
}
</style>