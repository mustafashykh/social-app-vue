<template>
  <div>
    <a-layout class="layout">
      <the-header></the-header>
      <a-layout-content class="site-layout-container">
      <div class="site-layout-content">
        <post></post>
        <post></post>
        <post></post>
      </div>
    </a-layout-content>
    </a-layout>
  </div>
</template>

<script>
import TheHeader from '../components/TheHeader.vue';
import Post from '../components/Post.vue';
import { common } from '../shared/constants';
import { onMounted } from '@vue/runtime-core';

export default {
  components: { TheHeader, Post },
  name: 'App',
  setup() {
    onMounted(() => {
      document.title = `${common.APP_NAME}`
    })
  }
}
</script>

<style lang="scss" scoped>
@import "../shared/scss/variables.scss";
.layout {
  background: $bg-body;
  overflow: auto;
}

.site-layout-content {
  min-height: 100vh;
  padding-top: 24px;
  background: $bg-body;
  border-left: 0.5px solid $border-color;
  border-right: 0.5px solid $border-color;
}

.site-layout-container {
  padding: 0 25vw;
}
</style>
