<script setup>
useHead({
  titleTemplate: (titleChunk) => {
    const titleBase = "OHZAO";
    return titleChunk ? `${titleChunk} - ${titleBase}` : titleBase;
  },
});
</script>

<template>
  <div>
    <!-- <BrannerAlert/> -->
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </div>
</template>