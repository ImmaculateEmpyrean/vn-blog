<template>
    <div class="searchBar">
        <input type="text" v-model="inputData" placeholder="Search" 
        @focus="inputFieldFocused = true" @blur="inputFieldFocused = false"
        >
        <svg width="25" height="25" viewBox="0 0 25 25" xmlns="http://www.w3.org/2000/svg"
        @click="$emit('search')"
        >
            <path fill-rule="evenodd" clip-rule="evenodd" d="M9.48021 17.0052L3.87604 22.6094C3.67892 22.8064 3.41163 22.917 3.13296 22.9169C2.8543 22.9168 2.58708 22.806 2.3901 22.6089C2.19312 22.4118 2.08252 22.1445 2.08261 21.8658C2.08271 21.5871 2.19351 21.3199 2.39062 21.1229L7.99479 15.5188C6.69721 13.8435 6.08658 11.7368 6.28713 9.62724C6.48768 7.5177 7.48434 5.56381 9.07436 4.16302C10.6644 2.76224 12.7283 2.0198 14.8463 2.08674C16.9643 2.15368 18.9772 3.02497 20.4756 4.52336C21.974 6.02175 22.8453 8.03469 22.9122 10.1527C22.9792 12.2707 22.2367 14.3346 20.836 15.9246C19.4352 17.5146 17.4813 18.5113 15.3717 18.7118C13.2622 18.9124 11.1555 18.3018 9.48021 17.0042V17.0052ZM8.33333 10.4167C8.33333 12.0743 8.99181 13.664 10.1639 14.8361C11.336 16.0082 12.9257 16.6667 14.5833 16.6667C16.2409 16.6667 17.8306 16.0082 19.0027 14.8361C20.1748 13.664 20.8333 12.0743 20.8333 10.4167C20.8333 8.75909 20.1748 7.16937 19.0027 5.99727C17.8306 4.82517 16.2409 4.16669 14.5833 4.16669C12.9257 4.16669 11.336 4.82517 10.1639 5.99727C8.99181 7.16937 8.33333 8.75909 8.33333 10.4167Z" />
        </svg>

        <div class="accentBar"></div>
    </div>
</template>

<script>
export default {
    name: "SearchBar",
    data(){
        return{
            inputData: '',
            inputFieldFocused: false
        }
    },
    watch:{
        inputFieldFocused(newValue){
            let accentBar = this.$el.querySelector('.searchBar .accentBar');
            this.$emit('inputFieldFocused',newValue);

            if(newValue === true)
                accentBar.style.width="100%";
            else
                accentBar.style.width="0%";
        }
    }
}
</script>

<style lang="scss" scoped>
@use '../../assets/scss/setting' as *;

.searchBar{
    position: relative;
    background-color: map-get($dark,"darkest");
    padding: var(--spacing-normal);

    display: flex;
    justify-content: space-between;
    gap: var(--spacing-normal);

    .accentBar{
        transition: width ease-in-out 0.5s;

        position: absolute;    
        left: 0;
        bottom: 0;

        width: 0%;
        height: 10%;
        background-color: $accent;
    }
}

input{
    flex: 1 1 100%;

    background-color: inherit;
    border: none;
    color: $light;

    &:focus{
        outline: none;
    }
}
svg{
    fill: $light;
    cursor: pointer
}
</style>