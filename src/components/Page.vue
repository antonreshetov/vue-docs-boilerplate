<template>
  <div class="page">
    <div class="page__inner">
      <!-- eslint-disable vue/no-v-html -->
      <div
        id="html"
        v-html="html"
      />
    </div>
  </div>
</template>

<script>

export default {
  name: 'Page',

  data () {
    return {
      html: ''
    }
  }
}
</script>

<style lang="scss">
.page {
  padding-left: $sidebarWidth;
  margin-top: $navbarHeight;
  &__inner {
    padding: $padding;
    max-width: $contentWidth;
    margin: 0;
  }
  div[id^="demo"] {
    + div[id^="demo"] {
      margin-top: 30px;
    }
  }
}
</style>
