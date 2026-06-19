<script setup>
useHead({
  meta: [
    { name: 'viewport', content: 'width=device-width, initial-scale=1' }
  ],
  link: [
    { rel: 'icon', href: '/icons/web/favicon.ico' }
  ],
  htmlAttrs: {
    lang: 'en'
  }
})

const title = 'Dillon\'s Blog'
const description = ''

useSeoMeta({
  title,
  description,
  ogTitle: title,
  ogDescription: description,
  ogImage: 'https://ui.nuxt.com/assets/templates/nuxt/starter-light.png',
  twitterCard: 'summary_large_image'
})
</script>

<template>
  <UApp>
    <UHeader :toggle="false">
      <template #title>
        <img
          src="/icons/web/icon-512.png"
          class="h-8"
          alt="Dillon Hartley"
        >
      </template>
      <template #right>
        <UTooltip
          text="Open on GitHub"
        >
          <UButton
            color="neutral"
            variant="ghost"
            to="https://github.com/d-llon"
            target="_blank"
            icon="i-simple-icons-github"
            aria-label="GitHub"
          />
        </UTooltip>
      </template>
    </UHeader>
    <UMain class="mb-8">
      <NuxtPage />
    </UMain>
  </UApp>
</template>
