<script lang="ts">
definePageMeta({
  layout: 'hoge-layout',
});
</script>

<script setup lang="ts">
const pageName = 'hoge-page';
</script>

<template>
  <div class="hoge-page">
    <div>{{ pageName }}</div>
  </div>
</template>

<style scoped>
.hoge-page {
  font-size: 16px;
}
</style>
