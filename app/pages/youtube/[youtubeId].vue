<script lang="ts" setup>
const youtubeId = useRoute().params.youtubeId;
const embedUrl = `https://www.youtube-nocookie.com/embed/${youtubeId}?rel=0`;
// example video: https://www.youtube-nocookie.com/embed/BeyQ4hPDPUI
// example video with wrong audio track: https://www.youtube-nocookie.com/embed/KVT_ODZn9Ys
</script>

<template>
  <div>
    <iframe
      :src="embedUrl"
      width="560px"
      height="340px"
      allowfullscreen
      frameborder="0"
      className="video"
    >
    </iframe>
  </div>
</template>

<style></style>
