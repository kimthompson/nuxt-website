<template>
  <div class="container">
    <navbar/>
    <about/>
    <skills/>
    <bottom/>
  </div>
</template>

<script>
import Navbar from '../components/Navbar.vue'
import About from '../components/Homepage/About.vue'
import Skills from '../components/Homepage/Skills.vue'
import Bottom from '../components/Bottom.vue'

export default {
  components: {
    Navbar,
    About,
    Skills,
    Bottom
  }
}
</script>
