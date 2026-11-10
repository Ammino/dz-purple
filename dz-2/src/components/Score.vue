<script setup>
    const { score = 0 } = defineProps({
        score: Number,
    });
</script>

<template>
    <div class="header__hearts">
        <span class="header__hearts-text">{{ score }}</span>
        <span class="header__hearts-icon">❤</span>
    </div>
</template>

<style scoped>

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