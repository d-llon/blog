<script setup lang="ts">
const route = useRoute()

const { data: post } = await useAsyncData(() => {
  return queryCollection('blog').where('slug', '=', route.params.slug).first()
})
</script>

<template>
  <UContainer>
    <template v-if="post">
      <UPageHeader
        :title="post.title"
        :description="post.description"
      />
      <ContentRenderer
        :value="post"
      />
    </template>
    <UError
      v-else
      :error="{
        statusCode: 404,
        statusMessage: 'Page not found',
        message: 'The page you are looking for does not exist.'
      }"
    />
  </UContainer>
</template>
