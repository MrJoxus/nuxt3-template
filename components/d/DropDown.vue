<!-- https://daisyui.com/components/dropdown/ -->

<template lang="html">
  <details ref="detailsRef" class="dropdown mb-32" @click="modal = true">
    <summary class="m-1 btn">
      <slot name="title">
        {{ title }}
      </slot>
    </summary>
    <ul class="dropdown-content p-2 shadow z-[20] bg-base-100 rounded-box">
      <slot name="dropDownItems" />
    </ul>
    <dialog
      class="modal z-[10]"
      :class="{'modal-open': modal}"
      @click="closeDropdown"
    />
  </details>
</template>

<script setup lang="ts">
import { DetailsHTMLAttributes, ref } from 'vue'

defineProps<{
  title?: string
}>()

const detailsRef = ref<DetailsHTMLAttributes | null>(null)
const modal = ref(false)

function closeDropdown () {
  if (detailsRef.value) {
    detailsRef.value.open = false
    modal.value = false
  }
}
</script>

<style lang="scss">
.modal:not(dialog:not(.modal-open)), .modal::backdrop {
  @apply bg-transparent;
  animation: none;
}
</style>
