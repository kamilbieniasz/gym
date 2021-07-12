<template>
    <nav class="navbar" :class="{changeBackground: scrollPos > 50}">
        <a>O nas</a>
        <a>Cennik</a>
        <a>Zajęcia grupowe</a>
        <a>Trening personalny</a>
        <a>Kontakt</a>
    </nav>
</template>
<script>
import { ref, onMounted } from 'vue';

export default {
name: "Navbar",
setup(){
    const scrollPos = ref();

    const updateScroll = () => {
        scrollPos.value = window.scrollY;
    }

    onMounted(() => {
        window.addEventListener('scroll', updateScroll);
    })

    return {scrollPos};
}
}

</script>
<style lang="scss" scoped>
@import '../../assets/scss/style.scss';

.navbar{
    width: 100%;
    display: flex;
    justify-content: center;
    background-color: transparent;
    position: fixed;
    z-index:20;
    -webkit-box-shadow: $shadow-box; 
    box-shadow: $shadow-box;
    transition: 300ms ease-in-out;

    & > a {
        padding: 20px;
        color: $color-white;
        font-size: $bigger-font;
        transition: 300ms easy-in-out;
        cursor: pointer;
        text-shadow: 2px 2px $color-black;

        &:hover{
            transform: scale(1.1);
            transition: 300ms easy-in-out;
        }
    }

    &.changeBackground {
        background-color: #212121;
        transition: 300ms ease-in-out;
    }
}
    
</style>
