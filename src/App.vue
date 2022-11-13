<template>
  <Navbar />
  <Hero />
  <About />
  <Cast />
  <Ticket />

</template>

<script>
import Navbar from './components/NavbarComp.vue'
import Hero from './components/HeroSection.vue'
import Cast from './components/CastSection.vue'
import Ticket from './components/TicketSection.vue'
import About from './components/AboutSection.vue'

export default {
  components:{
    Navbar,
    Hero,
    Cast,
    Ticket,
    About
  }
}
</script>

<style>

</style>
