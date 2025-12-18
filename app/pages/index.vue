<template>
  <div className="search-container">
    <USelect v-model="value" :items="items" color="secondary" />
    <UInput color="secondary" />
    <UButton
      icon="i-lucide-search"
      size="md"
      color="secondary"
      variant="subtle"
    />
  </div>
</template>

<script lang="ts" setup>
const items = ref(["YouTube"]);
const value = ref("YouTube");
</script>

<style></style>
