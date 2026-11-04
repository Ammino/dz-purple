<script setup>
// const props = defineProps({
//     label: {
//         type: String,
//         required: true,
//     },
//     value: {
//         type: String,
//         required: true,
//     },
// });
const { label = "Не задан", value = "-" } = defineProps({
    label: String,
    value: String,
});
</script>

<template>
    <div class="stat">
        <div class="stat-name">{{ label }}</div>
        <div class="stat-value">{{ value }}</div>
    </div>
</template>

<style scoped>
    .stat {
        display: flex;
        justify-content: space-between;
        align-items: center;
        font-size: 28px;
        gap: 10px;
    }
    .stat-name {
        font-weight: 700;
    }
    .stat-value {
        font-weight: 500;
    }
</style>