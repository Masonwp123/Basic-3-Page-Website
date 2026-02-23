<script setup>
defineProps({
  text: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="text">{{ text }}</div>
</template>

<style scoped>
.text {
  text-align: left;
}
</style>