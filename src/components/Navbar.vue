<template>
  <header class="navbar">
    <div class="navbar__inner">
      <div class="navbar__site-name">
        {{ config.title }}
      </div>
      <div class="navbar__search">
        <!-- TODO: search -->
      </div>
      <div class="navbar__links">
        <!-- TODO: links -->
      </div>
    </div>
  </header>
</template>

<script>
import config from '../config'

export default {
  name: 'Navbar',

  data () {
    return {
      config
    }
  }
}
</script>

<style lang="scss">
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: $navbarHeight;
  background-color: #fff;
  z-index: 1010;
  @include boxShadow();
  &__inner {
    height: $navbarHeight;
    display: flex;
    align-items: center;
  }
  &__site-name {
    width: $sidebarWidth;
    padding-left: $padding;
    border-right: 1px solid $color-border;
    font-weight: 600;
  }
  &__search {
    flex-grow: 1;
    padding-left: $padding;
  }
  &__links {
    display: flex;
    flex-grow: 2;
    justify-content: flex-end;
    padding-right: $padding;
  }
}
</style>
