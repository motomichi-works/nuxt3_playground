<template>
  <div class="default-layout">
    <div>default-layout</div>
    <ul>
      <li
        v-for="(item, index) in [
          { name: 'home', path: '/'},
        ]"
        :key="index"
      >
        <NuxtLink :to="item.path">{{ item.name }}</NuxtLink>
      </li>
    </ul>
    <slot />
  </div>
</template>
