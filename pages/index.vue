<template>
  <div class="container mx-auto p-4">
    <div class="card w-96 bg-primary text-primary-content mx-auto">
      <div class="card-body">
        <h2 class="card-title">
          {{ $t('welcome') }}
        </h2>
        <p>{{ $t('tongueTwister') }}</p>
        <div class="card-actions justify-end">
          <LanguageSwitcher />
          <ThemeSwitcher />
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>

</script>
<style lang="">

</style>
