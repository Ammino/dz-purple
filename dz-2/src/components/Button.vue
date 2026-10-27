<script setup>

</script>

<template>
    <button class="button">
        <slot />
    </button>
</template>

<style scoped>
    .button {
        --button-bg: #008BFE;
        --button-bg-hover: #006FCB;
        --button-color: #fff;

        display: inline-block;
        background-color: var(--button-bg);
        color: var(--button-color);
        border: none;
        outline: none;
        cursor: pointer;
        font-size: 24px;
        font-weight: 400;
        line-height: 1.5;
        text-align: center;
        padding: 16px 32px;
        border-radius: 100px;
        transition: all 0.3s ease;
    }
    .button:hover {
        background-color: var(--button-bg-hover);
    }
</style>