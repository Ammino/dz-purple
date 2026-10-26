<script setup>
    import { ref } from 'vue'
    const today = ref(new Date().toLocaleDateString('ru-RU'))
</script>

<template>
    <div>{{ today }}</div> 
</template>

<style scoped>
  
</style>