<script lang="ts">
</script>

<script setup lang="ts">
const pageName = 'index-page';
const state = reactive({
  value: -1,
});
const onClickCustomItem = (value: number) => {
  state.value = value;
};
</script>

<template>
  <div class="index-page">
    <div>{{ pageName }}</div>

    <client-only>
      <v-select
        v-model="state.value"
        :items="[
          { id: -1, name: '選択してください', value: -1 },
          { id: 1, name: 'name1', value: 1 },
          { id: 2, name: 'name2', value: 2 },
        ]"
        item-title="name"
      >
        <template v-slot:selection="{ item }">
          <div class="selected-view">
            選択されたアイテム: {{ item.value }}: {{ item.title }}
          </div>
        </template>
        <template v-slot:item="{ item }">
          <div
            class="custom-item-view"
            @click="onClickCustomItem(item.value)"
          >
            カスタムアイテム: {{ item.title }}
          </div>
        </template>
      </v-select>
    </client-only>
  </div>
</template>

<style scoped lang="scss">
.index-page {
  font-size: 16px;
}

.selected-view {
  color: #ff0000;
}

.custom-item-view {
  color: #339933;
}
</style>