<template>
  <Navbar />
  <div class="scrollContainer">
    <Home />
  </div>
</template>

<script>
import Navbar from './components/partials/Navbar';
import Home from './components/Home';

export default {
  name: 'App',
  components: {
    Navbar,
    Home
  }
}
</script>

<style>
body{
  margin: 0;
  padding: 0;
}
</style>
