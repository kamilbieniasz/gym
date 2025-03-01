<template>
  <nav id="navbar" class="navbar" ref="navbar" :class="{'active': $props.navbarActive, 'visible': $props.navbarVisible}">
    <h1>
      <a @click="scrollToSection($props.homeRef)">
        <fa class="icon" icon="dumbbell"/>
        <span>GymMaster</span>
      </a>
    </h1>
    <div class="links">
      <a @click="scrollToSection($props.aboutUsRef)">O nas</a>
      <a @click="scrollToSection($props.passesRef)">Cennik</a>
      <a @click="scrollToSection($props.groupClassesRef)">Zajęcia grupowe</a>
      <a @click="scrollToSection($props.personalTrainingRef)">Trening personalny</a>
      <a @click="scrollToSection($props.contactRef)">Kontakt</a>
    </div>
  </nav>
</template>
<script>
import {ref} from 'vue';

export default {
  name: "Navbar",
  props: ['homeRef', 'aboutUsRef', 'passesRef', 'groupClassesRef', 'personalTrainingRef', 'contactRef', 'navbarActive', 'navbarVisible'],
  emits: ['closeNavbar'],
  setup(props, {emit}) {
    const scrollPos = ref();

    const scrollToSection = (selector) => {
      selector?.$el?.scrollIntoView({
        behavior: "smooth",
        block: window.innerWidth <= 768 ? "start" : "end"
      });
      closeNavbar();
    }

    const closeNavbar = () => {
      console.log('closeNavbar');
      emit('closeNavbar');
    }

    return {
      scrollPos,
      scrollToSection,
      closeNavbar
    };
  }
}

</script>
<style lang="scss" scoped>
@import '../../assets/scss/style.scss';

.navbar {
  width: calc(100dvw - $scrollbarWidth);
  height: fit-content;
  display: flex;
  justify-content: center;
  position: fixed;
  z-index: 20;
  border-bottom: 2px solid $color-red;
  transform: translateX(-100dvw);
  transition: 300ms ease-in-out;
  opacity: 0;
  flex-direction: column;
  background-color: $color-dark;
  box-shadow: 0 5px 15px -5px $color-black;
  padding: 0 0.5rem;

  @include respond-to(min-width, 768px) {
    height: $navbarHeight;
    transform: translateX(0);
    opacity: 1;
    flex-direction: row;
    justify-content: space-between;
    background-color: transparent;
    transition: 300ms ease-in-out;
    padding: 0 1rem;
  }

  &.active {
    background-color: $color-dark;
    transition: 300ms ease-in-out;
  }

  &.visible {
    transform: translate(0);
    opacity: 1;
  }

  & > div.links {
    display: flex;
    flex-direction: column;

    @include respond-to(min-width, 768px) {
      flex-direction: row;
    }
  }

  & > h1 {
    margin: 0;
    height: 100%;
    display: flex;
  }

  & > div.links,
  & > h1 {
    font-size: 1.5rem;

    @include respond-to(min-width, 768px) {
      font-size: 1rem;
    }

    @include respond-to(min-width, 1024px) {
      font-size: 1.5rem;
    }

    & > a {
      padding: 1rem 0.25rem;
      color: $color-white;
      transition: 300ms easy-in-out;
      cursor: pointer;
      text-shadow: 2px 2px $color-black;
      display: flex;
      align-items: center;
      white-space: nowrap;

      @include respond-to(min-width, 768px) {
        padding: 1rem;

        &:hover {
          transform: scale(1.1);
          transition: 300ms ease-in-out;
        }
      }

      &:first-child {
        display: flex;

        & > .icon {
          margin-right: 10px;
        }

        & > h2 {
          margin: 0;
        }
      }
    }
  }
}

</style>
