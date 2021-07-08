<template>
  <Navbar />
  <div class="scrollContainer">
    <Home />
    <AboutUs />
  </div>
</template>

<script>
import Navbar from './components/partials/Navbar';
import Home from './components/Home';
import AboutUs from './components/AboutUs';

export default {
  name: 'App',
  components: {
    Navbar,
    Home,
    AboutUs
  }
}
</script>

<style>
body{
  margin: 0;
  padding: 0;
}
</style>
