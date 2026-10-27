<script setup>
  import Header from './components/header.vue'
  import Button from './components/Button.vue'
</script>

<template>
  <Header />
  <div class="welcomebtn">
    <div class="welcomebtn__content">
      <Button>Начать игру</Button>
    </div>
  </div>
</template>

<style scoped>
.welcomebtn {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 24px 62px;
  height: 100%;
}
.welcomebtn__content {
  width: 335px;
  margin: 0 auto;
}
.welcomebtn .button {
  width: 100%;
}
</style>