<script setup>

</script>

<template>
    <header class="header">
        <div class="header__grid">
            <div class="header__logo">ЗАПОМНИ СЛОВО</div>
            <div class="header__hearts">
                <span class="header__hearts-text">100</span>
                <span class="header__hearts-icon">❤</span>
            </div>
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

.header__hearts {
    display: flex;
    align-items: center;
    background-color: var(--color-bg);
    gap: 10px;
    font-size: 16px;
    font-weight: 400;
    line-height: 1.5;
    color: var(--color-primary);
    background-color: var(--color-blue);
    box-shadow: var(--shadow);
    border-radius: 36px;
    padding: 12px 24px;
}

.header__hearts-icon {
    width: 24px;
    height: 24px;
    display: flex;
    align-items: center;
    justify-content: center;
}
</style>