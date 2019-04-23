<template>
  <div class="theme-container">
    <Navbar />
    <Sidebar />
    <Page />
  </div>
</template>

<script>
import Navbar from './Navbar'
import Sidebar from './sidebar/Sidebar'
import Page from './Page'

export default {
  name: 'Layout',

  components: {
    Navbar,
    Sidebar,
    Page
  },

  data () {
    return {

    }
  }
}
</script>

<style lang="scss">
@import '../assets/scss/base';
</style>
