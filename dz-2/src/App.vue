<script setup>
  import { ref } from 'vue'
  import Header from './components/header.vue'
  // import Button from './components/Button.vue'
  import Card from './components/Card.vue'
  
</script>

<template>
  <Header />
  <!-- <div class="welcomebtn">
    <div class="welcomebtn__content">
      <Button>Начать игру</Button>
    </div>
  </div> -->
  <div class="game">
    <div class="cardlist">
      <Card status="default" />
      <Card status="flip" />
      <Card status="correct" />
      <Card status="incorrect" />
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

.game {
  padding: 24px 62px;
  height: 100%;
}

.cardlist {
  display: grid;
  grid-template-columns: repeat(4, 250px);
  gap: 30px;
}
</style>