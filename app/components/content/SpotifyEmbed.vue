<script setup lang="ts">
defineProps({
  trackId: String
})
</script>

<template>
  <iframe
    data-testid="embed-iframe"
    style="border-radius:12px"
    :src="`https://open.spotify.com/embed/track/${trackId}?utm_source=generator&theme=0&si=a575469670f34f01`"
    width="100%"
    height="152"
    frameBorder="0"
    allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"
    loading="lazy"
  />
</template>

<style scoped>

</style>
