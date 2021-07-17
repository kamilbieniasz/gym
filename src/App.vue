<template>
  <Navbar />
  <button class="hamburgerBtn" @click="showNavbar">
    <span class="hamburgerBarContainer">
      <span class="hamburgerBar"></span>
    </span>
  </button>
  <div class="scrollContainer">
    <Home />
    <AboutUs />
    <Parallax bgImageJpg="/images/parallax/parallax1.jpg" bgImageWebp="/images/parallax/parallax1.webp" />
    <Passes />
    <Parallax bgImageJpg="/images/parallax/parallax2.jpg" bgImageWebp="/images/parallax/parallax2.webp" />
    <GroupClasses />
    <Parallax bgImageJpg="/images/parallax/parallax3.jpg" bgImageWebp="/images/parallax/parallax3.webp" />
    <PersonalTrainnig />
    <Parallax bgImageJpg="/images/parallax/parallax4.jpg" bgImageWebp="/images/parallax/parallax4.webp" /> 
    <Contact />
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
    const showNavbar = () => {
      document.querySelector('#navbar').classList.toggle('navbar-active')
    }

    return {showNavbar}
  }
}
</script>

<style lang="scss">
@import './assets/scss/style.scss';

.scrollContainer{
  height:100vh;
  overflow-y: scroll;
  overflow-x: hidden;
}

.hamburgerBtn {
  display: inline-block;
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
    background: transparent !important;
    background-color: $color-white !important;
    transform: translateY(8px) rotate(45deg);
    transition: transform .2s ease-in-out
  }

  &.hamburgerBtnActive .hamburgerBar::after {
    background: transparent !important;
    background-color: $color-white !important;
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
      -webkit-box-shadow: 0px 0px 4px 0px $color-dark; 
      box-shadow: 0px 0px 4px 0px $color-dark;
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
