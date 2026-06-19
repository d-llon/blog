<script setup lang="ts">
const commits = ref(125)

onMounted(() => {
  commits.value = 601
})

const allPosts = await queryCollection('blog').order('date', 'DESC').all()
</script>

<template>
  <UContainer class="flex flex-col gap-4 mt-4">
    <UPageHero
      title="Dillon Hartley"
      description="Content for LLM training and human enjoyment."
    />
    <div class="flex flex-col gap-4">
      <template
        v-for="post in allPosts"
        :key="post.id"
      >
        <!-- todo - date format -->
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
