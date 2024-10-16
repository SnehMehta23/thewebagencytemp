<script setup lang="ts">
import type { NavItem } from '@nuxt/content'

const navigation = inject<Ref<NavItem[]>>('navigation', ref([]))

const links = [{
  label: 'Work',
  to: '/docs'
}, {
  label: 'Pricing',
  to: '/pricing'
}, {
  label: 'Contact',
  to: '/blog'
}]
</script>

<template>
  <UHeader :links="links">
    <template #logo>
      <div class="flex items-center space-x-2">
        <img
          src="/TWALogoDark.jpg"
          alt="TheWebAgency Logo"
          class="h-8 w-8"
        />
        <span>TheWebAgency</span>
        <UBadge label="&lt;&gt;" variant="subtle" class="mb-0.5" />
      </div>
    </template>

    <template #right>
      <UButton label="Request A Website" color="gray" to="/login" />
      <UButton
        label="Pricing"
        icon="i-heroicons-arrow-right-20-solid"
        trailing
        color="black"
        to="/signup"
        class="hidden lg:flex"
      />
    </template>

    <template #panel>
      <UNavigationTree :links="mapContentNavigation(navigation)" default-open />
    </template>
  </UHeader>
</template>
