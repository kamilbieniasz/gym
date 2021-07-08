<template>
  <Navbar />
  <div class="scrollContainer">
    <Home />
    <AboutUs />
    <Parallax />
    <Passes />
  </div>
</template>

<script>
import Navbar from './components/partials/Navbar';
import Home from './components/Home';
import AboutUs from './components/AboutUs';
import Parallax from './components/Parallax';
import Passes from './components/Passes';

export default {
  name: 'App',
  components: {
    Navbar,
    Home,
    AboutUs,
    Parallax,
    Passes
  }
}
</script>

<style>
body{
  margin: 0;
  padding: 0;
}
</style>
