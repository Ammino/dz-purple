<script setup>
  import { ref } from 'vue'
  import Header from './components/header.vue'
  // import Button from './components/Button.vue'
  import Card from './components/Card.vue'

  const cards = ref([
    { id: 1, status: 'default' },
    { id: 2, status: 'flip' },
    { id: 3, status: 'correct' },
    { id: 4, status: 'incorrect' },
  ])

  function flipCard(card) {
    card.status = 'flip'
  }

  function changeCardStatus(card, status) {
    card.status = status
  }
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
      <Card
        v-for="card in cards"
        :key="card.id"
        :status="card.status"
        @flip="flipCard(card)"
        @change-status="changeCardStatus(card, $event)"
      />
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