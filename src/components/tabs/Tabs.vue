<template>
  <div class="tabs">
    <div class="tabs__labels">
      <div
        v-for="label in tabsLabels"
        :key="label"
        class="tabs__labels-item"
        :class="{'active': isActive(label)}"
        @click="onChangeTab(label)"
      >
        {{ label }}
      </div>
    </div>
    <div class="tabs__body">
      <slot />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Tabs',

  model: {
    event: 'change',
    prop: 'active'
  },

  props: {
    active: {
      type: String,
      default: ''
    }
  },

  data () {
    return {
      value: '',
      tabsLabels: []
    }
  },

  watch: {
    active () {
      this.value = this.active
    },
    value () {
      this.$emit('change', this.value)
    }
  },

  created () {
    this.value = this.active
  },

  mounted () {
    this.getTabsLabels()
  },

  methods: {
    onChangeTab (tab) {
      this.$emit('change', tab)
    },
    getTabsLabels () {
      this.tabsLabels = this.$children.map(item => item.name)
    },
    isActive (name) {
      return name === this.value
    }
  }
}
</script>

<style lang="scss">
.tabs {
  $r: &;
  &__labels {
    display: flex;
    &-item {
      padding: 5px;
      border-bottom: 2px solid transparent;
      text-transform: uppercase;
      font-size: 11px;
      cursor: pointer;
      &.active {
        border-bottom: 2px solid $color-accent;
      }
      + #{$r}__labels-item {
        margin-left: 10px;
        padding: 5px 5px;
      }

    }
  }
  &__item {
    &-body {
      box-sizing: border-box;
    }
    margin-top: 15px;
    pre, code {
      margin-top: 0;
    }
    pre {
      margin-top: -15px;
    }
  }
}
</style>
