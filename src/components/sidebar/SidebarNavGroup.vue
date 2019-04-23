<template>
  <div class="sidebar-nav__group">
    <div class="sidebar-nav__group-name">
      {{ items.name }}
    </div>
    <SidebarNavItem
      v-for="(i, index) in items.children"
      :key="index"
      :item="i"
    />
  </div>
</template>

<script>
import SidebarNavItem from './SidebarNavItem'

export default {
  name: 'SidebarNavGroup',

  components: {
    SidebarNavItem
  },

  props: {
    items: {
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
.sidebar-nav__group {
  + .sidebar-nav__group {
    margin-top: 20px;
  }
  &-name {
    padding-bottom: 10px;
    color: $color-text-primary;
    font-weight: 800;
  }
}
</style>
