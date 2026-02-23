<script setup>

import CleanImage from './../components/CleanImage.vue'
import CleanText from './../components/CleanText.vue'

defineProps({
  image: {
    type: String,
    required: true
  },
  text: {
    type: String,
    required: true
  },
  right: {
    type: Boolean
  }
})
</script>

<template>
  <div v-if="right" class="alignRight">
      <CleanText :text="text"/>
      <CleanImage :image="image"/>
  </div>
  <div v-else class="alignLeft">
    <CleanImage :image="image"/>
    <CleanText :text="text"/>
  </div>
</template>

<style scoped>
  .alignLeft {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    position: fixed;
    left: 0;
  }
  .alignRight {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    position: fixed;
    right: 0;
  }
</style>