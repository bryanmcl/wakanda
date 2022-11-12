<template>
  <Navbar />
  <Hero />
  <Cast />
  <Ticket />

</template>

<script>
import Navbar from './components/NavbarComp.vue'
import Hero from './components/HeroSection.vue'
import Cast from './components/CastSection.vue'
import Ticket from './components/TicketSection.vue'

export default {
  components:{
    Navbar,
    Hero,
    Cast,
    Ticket
  }
}
</script>

<style>

</style>
