<template>
  <div>
    <div class="grid-container relative container mx-auto min-h-screen">
      <div class="grid-item-nav sticky flex justify-between top-0 h-screen overflow-hidden">
        <div class="flex-1">
          <div class="h-16">
            NAV HEADER
          </div>
          <div class="h-[calc(100%_-_64px)] overflow-scroll pr-4">
            NAV MENU
          </div>
        </div>
        <div class="nav-shadow" />
      </div>
      <div class="grid-item-header sticky top-0 pl-8 bg-white">
        <div class="h-full">
          HEADER
        </div>
      </div>
      <div class="grid-item-main p-8 pt-0">
        <slot />
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>

</script>

<style lang="scss">

.nav-shadow {
  @apply my-48;
  @apply w-0;
  box-shadow: 100px 0px 120px 120px #ababab52;
}

.grid-item-header {
  grid-area: header;
}

.grid-item-nav {
  grid-area: nav;
}

.grid-item-main {
  grid-area: content;
}

.grid-container {
  display: grid;
  grid-template-columns: 256px 1fr;
  grid-template-rows: 60px 1fr;
  grid-template-areas:
    "nav header"
    "nav content";
}
</style>
