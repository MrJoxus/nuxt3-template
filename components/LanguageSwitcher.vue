<template>
  <DDropDown class="dropdown-bottom dropdown-end" :title="currentLocale">
    <template #dropDownItems>
      <DMenu>
        <li v-for="locale in locales" :key="locale.title">
          <NuxtLink :to="switchLocalePath(locale.code)">
            {{ locale.title }}
          </NuxtLink>
        </li>
      </DMenu>
    </template>
  </DDropDown>
</template>

<script lang="ts" setup>
const switchLocalePath = useSwitchLocalePath()
const browserLocale = useBrowserLocale()
const cookieLocale = useCookieLocale()
const currentLocale = cookieLocale.value || browserLocale || ''

// TODO: get available locales from i18n
const locales = [
  {
    title: 'DE',
    code: 'de'
  },
  {
    title: 'EN',
    code: 'en'
  }
]

</script>
