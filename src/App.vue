<template>
  <nav-bar />
  <content-view />
  <footer-view />
</template>

<script>
import Navbar from './components/navbar/NavbarView.vue'
import Container from './components/container/ContentView.vue'
import Footer from './components/footer/FooterView.vue'

export default {
  name: 'App',
  components: {
    'nav-bar': Navbar,
    'content-view': Container,
    'footer-view': Footer,
  },

}
</script>

<style>
  * {
    margin: 0;
    box-sizing: border-box;
  }
  
</style>
