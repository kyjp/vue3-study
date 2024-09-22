<script setup>
defineProps({
  name: {
    type: String,
    required: true
  }
})
</script>
<template>
  <div class="card">{{ name }}</div>
</template>
<style scoped>
.card {
  box-shadow: 2px 2px 6px rgba(0, 0, 0, 0.4);
  border-radius: 5px;
  font-size: 2rem;
  padding: 16px;
}
</style>
