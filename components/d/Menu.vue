<template>
  <ul class="menu bg-base-100 w-56 rounded-box">
    <slot>
      <li v-for="item in menuItems" :key="item.title">
        <NuxtLink to="item.to">
          {{ item.title }}
        </NuxtLink>
      </li>
    </slot>
  </ul>
</template>

<script lang="ts" setup>
// TODO: add icon support
import { menuItem } from '@/types'

defineProps<{
  menuItems?: menuItem[]
}>()
</script>

<style lang="">

</style>
