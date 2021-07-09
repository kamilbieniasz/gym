<template>
  <Navbar />
  <div class="scrollContainer">
    <Home />
    <AboutUs />
    <Parallax backgroundImage="/images/parallax/parallax1.jpg" />
    <Passes />
    <Parallax backgroundImage="/images/parallax/parallax2.jpg" />
    <GroupClasses />
    <Parallax backgroundImage="/images/parallax/parallax3.jpg" />
    <PersonalTrainnig />
    <Parallax backgroundImage="/images/parallax/parallax4.jpg" />
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
    Contact
  }
}
</script>

<style>
body{
    margin:0;
    padding:0;
}
</style>
