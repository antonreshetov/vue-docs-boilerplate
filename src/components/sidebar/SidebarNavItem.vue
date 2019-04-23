<template>
  <div class="sidebar-nav__item">
    <RouterLink :to="item.path">
      {{ item.name }}
    </RouterLink>
  </div>
</template>

<script>
export default {
  name: 'SidebarNavItem',

  props: {
    item: {
      type: Object,
      default: () => {}
    }
  },

  data () {
    return {

    }
  }
}
</script>

<style lang="scss">
.sidebar-nav__item {
  a {
    margin-left: 10px;
    padding: 7px 0;
    text-decoration: none;
    color: $color-text-primary;
    display: block;
    &.active {
      color: $color-accent;
      border-right: 2px solid $color-accent;
    }
  }
}
</style>
