<script setup>
defineProps({
  image: {
    type: String,
    required: true
  }
})
</script>

<template>
  <img :src="image" alt="Page Image" class="image" />
</template>

<style scoped>
.image {
  max-width: 600px;
  height: auto;
}
</style>