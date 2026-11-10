<script setup>
  import Score from './Score.vue'
</script>

<template>
    <header class="header">
        <div class="header__grid">
            <div class="header__logo">ЗАПОМНИ СЛОВО</div>
            <Score/>
        </div>
    </header>
</template>

<style scoped>
.header {
    padding: 35px 62px;
}

.header__grid {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.header__logo {
    font-size: 16px;
    font-weight: 700;
    line-height: 1.5;
    color: var(--color-gray);
    letter-spacing: 0.12em;
    text-transform: uppercase;
}
</style>