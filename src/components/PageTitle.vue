<script setup>
defineProps({
  title: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="pageTitle">
    {{ title }}
  </div>
</template>

<style scoped>
.pageTitle {
  font-size: 48px;
  font-weight: 600;
  margin-bottom: 24px;
}
</style>