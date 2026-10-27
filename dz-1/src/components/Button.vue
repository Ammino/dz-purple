<script setup>
    // const props = defineProps({
    //     text: {
    //         type: String,
    //         required: true
    //     }
    // })
</script>

<template>
    <button class="button">
        <span class="button__icon">
            <slot name="icon"/>
        </span>
        <span class="button__text">
            <slot/>
        </span>
    </button>
</template>

<style scoped>
    .button {
        border: none;
        outline: none;
        display: inline-block;
        background: var(--gradient);
        color: var(--color-primary);
        border-radius: 10px;
        padding: 14px 13px;
        line-height: 1;
        font-size: 20px;
        font-weight: 600;
        cursor: pointer;
        transition: all 0.3s ease;

        &:hover {
            background: var(--gradient-inverted);
        }
    }
</style>