<template>
    <nav id="navbar" class="navbar" :class="{changeBackground: scrollPos > 50}">
        <a @click="scrollToSection('#home')">
            <fa class="icon" icon="dumbbell" />
            <h2>GymMaster</h2>
        </a>
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

    @include respond-to(max-width, 768px){
        transform: translateX(-101vw);
        opacity:0;
        flex-direction: column;
        background-color: $color-dark;
    }

    &.navbar-active{
        transform: translate(0);
        opacity: 1;
    }

    & > a {
        padding: 20px;
        color: $color-white;
        font-size: $bigger-font;
        transition: 300ms easy-in-out;
        cursor: pointer;
        text-shadow: 2px 2px $color-black;

        &:first-child{
            display:flex;
            & > .icon {
                margin: 0 10px;
            }

            & > h2{
                margin:0;
                font-size:26px;
            }

        }

        &:hover{
            transform: scale(1.1);
            transition: 300ms easy-in-out;
        }
    }

    &.changeBackground {
        background-color: $color-dark;
        transition: 300ms ease-in-out;
    }
}
    
</style>
