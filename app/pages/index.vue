<template>
  <div className="search-container">
    <USelect v-model="selectValue" :items="items" color="secondary" />
    <UInput
      color="secondary"
      placeholder="Enter a link or video id"
      v-model="inputValue"
      @keyup.enter="handleEnter"
    />
    <UButton
      icon="i-lucide-search"
      size="md"
      color="secondary"
      variant="subtle"
      class="button"
      @click="onClick"
    />
  </div>
</template>

<script lang="ts" setup>
const items = ref(["YouTube"]);
const selectValue = ref("YouTube");
const inputValue = ref("");
// Found the getYouTubeId function from https://gist.github.com/takien/4077195 by katai5plate
const getYouTubeId = (url: string) => {
  const [a, , b] = url
    .replace(/(>|<)/gi, "")
    .split(/(vi\/|v=|\/v\/|youtu\.be\/|\/embed\/)/);
  if (b !== undefined) {
    return b.split(/[^0-9a-z_-]/i)[0];
  } else {
    return a;
  }
};
async function onClick() {
  console.log(inputValue.value);
  let inputId;
  if (inputValue.value.length == 11) {
    inputId = inputValue.value;
  } else {
    inputId = getYouTubeId(inputValue.value);
  }
  await navigateTo(`/youtube/${inputId}`);
}
async function handleEnter() {
  console.log(inputValue.value);
  let inputId;
  if (inputValue.value.length == 11) {
    inputId = inputValue.value;
  } else {
    inputId = getYouTubeId(inputValue.value);
  }
  await navigateTo(`/youtube/${inputId}`);
}
</script>

<style></style>
