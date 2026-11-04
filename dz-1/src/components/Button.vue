<script setup>
    // const props = defineProps({
    //     text: {
    //         type: String,
    //         required: true
    //     }
    // })

    // defineOptions({
    //     inheritAttrs: false, //* отключаем автоматическое добавление атрибутов в компонент
    // })
</script>

<template>
    <button class="button">
        <slot name="icon"/>
        <span class="button__text">
            <slot/>
        </span>
        <!-- выведет классы, которые были переданы напрямую в компонент -->
        <!-- {{ $attrs["class"] }}  -->
    </button>
</template>

<style scoped>
    .button {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 10px;
        border: none;
        outline: none;
        background: var(--gradient);
        color: var(--color-primary);
        border-radius: 10px;
        padding: 9px 18px;
        min-height: 53px;
        line-height: 1;
        font-size: 20px;
        font-weight: 600;
        cursor: pointer;
        transition: all 0.3s ease;
    }
    .button:hover {
        background-color: var(--button-bg-hover);
    }
    .button__icon {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 33px;
        height: 33px;
    }
    .button__icon svg {
        width: 100%;
        height: 100%;
        object-fit: contain;
        object-position: center;
    }
    .button__text {
        display: flex;
        align-items: center;
        justify-content: center;
    }
</style>