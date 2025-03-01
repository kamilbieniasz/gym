<template>
    <nav id="navbar" class="navbar" ref="navbar" :class="{'active': $props.navbarActive}">
        <a @click="scrollToSection($props.homeRef)">
            <fa class="icon" icon="dumbbell" />
            <h2>GymMaster</h2>
        </a>
        <a @click="scrollToSection($props.aboutUsRef)">O nas</a>
        <a @click="scrollToSection($props.passesRef)">Cennik</a>
        <a @click="scrollToSection($props.groupClassesRef)">Zajęcia grupowe</a>
        <a @click="scrollToSection($props.personalTrainingRef)">Trening personalny</a>
        <a @click="scrollToSection($props.contactRef)">Kontakt</a>
    </nav>
</template>
<script>
import {ref} from 'vue';

export default {
name: "Navbar",
props: ['homeRef', 'aboutUsRef', 'passesRef', 'groupClassesRef', 'personalTrainingRef', 'contactRef', 'navbarActive'],
setup(){
    const scrollPos = ref();

    const scrollToSection = (selector) => {
      selector?.$el?.scrollIntoView({
        behavior: "smooth",
        block: "end"
      })
    }

    return {
      scrollPos,
      scrollToSection
    };
}
}

</script>
<style lang="scss" scoped>
@import '../../assets/scss/style.scss';

.navbar{
    width: calc(100dvw - $scrollbarWidth);
    height: $navbarHeight;
    display: flex;
    justify-content: center;
    background-color: transparent;
    position: fixed;
    z-index:20;
    border-bottom: 2px solid $color-red;
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

    &.active {
        background-color: $color-dark;
        transition: 300ms ease-in-out;
    }
}
    
</style>
