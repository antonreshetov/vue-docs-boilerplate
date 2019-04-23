<template>
  <div class="sidebar">
    <div class="sidebar__inner">
      <SidebarNav :data="nav" />
    </div>
  </div>
</template>

<script>
import SidebarNav from './SidebarNav'
import config from '@/config'

export default {
  name: 'Sidebar',

  components: {
    SidebarNav
  },

  data () {
    return {
      nav: config.navigation.sidebar
    }
  }
}
</script>

<style lang="scss">
.sidebar {
  position: fixed;
  width: $sidebarWidth;
  top: calc(#{$navbarHeight} + #{$padding});
  left: 0;
  bottom: 0;
  overflow-y: auto;
  border-right: 1px solid $color-border;
  &__inner {
    padding-left: $padding;
  }
}
</style>
