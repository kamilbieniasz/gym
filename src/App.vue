<template>
  <Navbar :home-ref="homeRef"
          :about-us-ref="aboutUsRef"
          :passes-ref="passesRef"
          :group-classes-ref="groupClassesRef"
          :personal-training-ref="personalTrainingRef"
          :contact-ref="contactRef"
          :navbar-active="scrollPos > ACTIVE_NAVBAR_THRESHOLD"/>
  <button class="hamburgerBtn" @click="showNavbar">
    <span class="hamburgerBarContainer">
      <span class="hamburgerBar"></span>
    </span>
  </button>
  <div ref="scrollWrapperRef" class="scrollContainer" @scroll="handleScroll">
    <Home ref="homeRef" />
    <AboutUs ref="aboutUsRef" />
    <Parallax background-image="parallax1.webp" />
    <Passes ref="passesRef" />
    <Parallax background-image="parallax2.webp" />
    <GroupClasses ref="groupClassesRef" />
    <Parallax background-image="parallax3.webp" />
    <PersonalTrainnig ref="personalTrainingRef" />
    <Parallax background-image="parallax4.webp" />
    <Contact ref="contactRef" />
  </div>
</template>

<script>
import Navbar from './components/partials/Navbar';
import Home from './components/Home';
import AboutUs from './components/AboutUs';
import Parallax from './components/Parallax';
import Passes from './components/Passes';
import GroupClasses from './components/GroupClasses';
import PersonalTrainnig from './components/PersonalTraining';
import Contact from './components/Contact';
import {ref} from "vue";

export default {
  name: 'App',
  components: {
    Navbar,
    Home,
    AboutUs,
    Parallax,
    Passes,
    GroupClasses,
    PersonalTrainnig,
    Contact,
  },
  setup(){
    const homeRef = ref();
    const aboutUsRef = ref();
    const passesRef = ref();
    const groupClassesRef = ref();
    const personalTrainingRef = ref();
    const contactRef = ref();
    const scrollWrapperRef = ref();
    const scrollPos = ref(0);

    const ACTIVE_NAVBAR_THRESHOLD = 100;

    const showNavbar = () => {
      document.querySelector('#navbar').classList.toggle('navbar-active')
    }

    const handleScroll = () => {
      console.log('scrollWrapperRef.value?.scrollTop', scrollWrapperRef.value?.scrollTop);
      scrollPos.value = scrollWrapperRef.value?.scrollTop;
    }

    return {
      homeRef,
      aboutUsRef,
      passesRef,
      groupClassesRef,
      personalTrainingRef,
      contactRef,
      scrollWrapperRef,
      scrollPos,
      ACTIVE_NAVBAR_THRESHOLD,
      showNavbar,
      handleScroll,
    }
  }
}
</script>

<style lang="scss">
@import './assets/scss/mixins';
@import './assets/scss/colors';
@import './assets/scss/general';
@import './assets/scss/reusable';

.scrollContainer{
  @extend %scrollbar;

  height: 100vh;
  overflow-y: scroll;
  overflow-x: hidden;
}

.hamburgerBtn {
  cursor: pointer;
  background-color: transparent;
  border: 0;
  margin: 0;
  z-index: 21;
  display: none;
  outline: none;
  position: fixed;
  top:5px;
  right:5px;


  @include respond-to(max-width, 768px) {
    display: block;
  }

  &.hamburgerBtnActive .hamburgerBar {
    background: transparent !important;
    -webkit-box-shadow: none !important; 
    box-shadow: none !important;
  }

  &.hamburgerBtnActive .hamburgerBar::before {
    background-color: $color-white;
    transform: translateY(8px) rotate(45deg);
    transition: transform .2s ease-in-out
  }

  &.hamburgerBtnActive .hamburgerBar::after {
    background-color: $color-white;
    transform: translateY(-8px) rotate(-45deg);
    transition: transform .2s ease-in-out
  }

  & > .hamburgerBarContainer {
    width: 25px;
    height: 20px;
    display: inline-block;
    position: relative;

    @mixin hamburgerBarStyle {
      width: 100%;
      height: 3px;
      background: $color-white;
      position: absolute;
      z-index: 0;
      box-shadow: 0 0 4px 0 $color-dark;
    }

    .hamburgerBar {
      @include hamburgerBarStyle;
      left: 0;
      top: 50%;
      transform: translateY(-50%);

      &:before,
      &:after {
        @include hamburgerBarStyle;
        content: '';
        left: 0;
        transition: transform .2s ease-in-out
      }

      &:before {
        top: -8px;
      }

      &:after {
        top: 8px;
      }
    }
  }
}
</style>
