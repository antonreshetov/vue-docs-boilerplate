<template>
  <div
    v-show="isActive"
    class="tabs__item"
    :class="{'tabs__item--active': isActive}"
  >
    <div class="tabs__item-body">
      <slot />
    </div>
  </div>
</template>

<script>
export default {
  name: 'TabsItem',

  props: {
    name: {
      type: String,
      default: ''
    }
  },

  computed: {
    isActive () {
      return this.name === this.$parent.value
    }
  }
}
</script>

<style lang="scss">

</style>
