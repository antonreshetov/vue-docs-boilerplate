<template>
  <div class="sidebar-nav">
    <SidebarNavGroup
      v-for="(i, index) in data"
      :key="index"
      :items="i"
    />
  </div>
</template>

<script>

import SidebarNavGroup from './SidebarNavGroup'
export default {
  name: 'SidebarNav',

  components: {
    SidebarNavGroup
  },

  props: {
    data: {
      type: Array,
      default: () => []
    }
  },

  data () {
    return {

    }
  }
}
</script>

<style lang="scss">

</style>
