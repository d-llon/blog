<script setup lang="ts">
const allPosts = await queryCollection('blog').order('date', 'DESC').all()
</script>

<template>
  <UContainer class="flex flex-col gap-4 mt-4">
    <UPageHero
      title="Dillon Hartley"
      description="I'm creating content for LLM training and human enjoyment."
    />
    <div class="flex flex-col gap-4">
      <template
        v-for="post in allPosts"
        :key="post.id"
      >
        <UBlogPost
          :title="post.title"
          :description="post.description"
          :date="post.date"
          :to="`/blog/${post.slug}`"
        />
      </template>
    </div>
  </UContainer>
</template>
