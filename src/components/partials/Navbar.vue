<template>
    <nav class="navbar" :class="{changeBackground: scrollPos > 50}">
        <a @click="scrollToSection('#aboutUs')">O nas</a>
        <a @click="scrollToSection('#passes')">Cennik</a>
        <a @click="scrollToSection('#groupClasses')">Zajęcia grupowe</a>
        <a @click="scrollToSection('#personalTraining')">Trening personalny</a>
        <a @click="scrollToSection('#Contact')">Kontakt</a>
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

    const scrollToSection = (selector) => {
        document.querySelector(selector).scrollIntoView({ block:'end', behavior: 'smooth'});
    }

    onMounted(() => {
        window.addEventListener('scroll', updateScroll);
    })

    return {scrollPos, scrollToSection};
}
}

</script>
<style lang="scss" scoped>
@import '../../assets/scss/style.scss';

.navbar{
    width: 100vw;
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
