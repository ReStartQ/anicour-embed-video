<template>
  <div>
    <iframe
      :src="embedUrl"
      width="560px"
      height="340px"
      allowfullscreen
      frameborder="0"
      className="video"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    >
    </iframe>
  </div>
</template>

<script lang="ts" setup>
const youtubeId = useRoute().params.youtubeId;
const embedUrl = `https://www.youtube.com/embed/${youtubeId}?rel=0`;
// example video: https://www.youtube-nocookie.com/embed/BeyQ4hPDPUI
// example video with wrong audio track: https://www.youtube-nocookie.com/embed/KVT_ODZn9Ys
</script>

<style></style>
