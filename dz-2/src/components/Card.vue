<script setup>
    import { computed } from 'vue';
    import IconCheck from '../icons/IconCheck.vue';
    import IconNegative from '../icons/IconNegative.vue';

    const { status = 'default' } = defineProps({
        status: String,
    });

    const emit = defineEmits({
        flip() {
            return true;
        },
        changeStatus(nextStatus) {
            return nextStatus === 'correct' || nextStatus === 'incorrect';
        },
    });

    function onFlip() {
        if (status !== 'default') return;
        emit('flip');
    }

    function onChangeStatus(nextStatus) {
        emit('changeStatus', nextStatus);
    }
    const statusText = computed(() => {
        if (status === 'default') return 'Перевернуть';
        if (status === 'flip') return '';
        if (status === 'correct') return 'Завершено';
        if (status === 'incorrect') return 'Ошибка';
        return '';
    });

    const textCard = computed(() => {
        if (status === 'default') return 'School';
        if (status === 'flip') return 'Школа';
        if (status === 'correct') return 'Школа';
        if (status === 'incorrect') return 'Школа';
        return '';
    })
</script>

<template>
    <div class="card">
        <div class="card__number">01</div>
        <div class="card__status__icon" v-if="status !== 'default' || status !== 'flip'">
            <IconCheck v-if="status === 'correct'" />
            <IconNegative v-if="status === 'incorrect'" />
        </div>
        <div class="card__word">{{ textCard }}</div>

        <button class="card__status" v-if="status !== 'flip'" type="button" @click="onFlip">{{ statusText }}</button>

        <div class="card__btns" v-if="status === 'flip'">
            <button class="card__btncheck" type="button" @click="onChangeStatus('incorrect')">
                <IconNegative />
            </button>
            <button class="card__btncheck" type="button" @click="onChangeStatus('correct')">
                <IconCheck />
            </button>
        </div>
    </div>
</template>

<style scoped>
.card {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: stretch;
    justify-content: center;
    width: 100%;
    max-width: 250px;
    aspect-ratio: 250/376;
    background-color: var(--color-bg);
    border-radius: 16px;
    box-shadow: var(--shadow-card);
    transition: box-shadow 0.3s ease-in-out;
}
.card:hover {
    box-shadow: var(--shadow-card-hover);
}
.card::after {
    content: '';
    position: absolute;
    top: 28px;
    bottom: 28px;
    left: 19px;
    right: 19px;
    border-radius: 12px;
    border: 1px solid var(--color-blue);
    z-index: 1;
}
.card__number {
    position: absolute;
    left: 35px;
    top: 22px;
    z-index: 2;
    background-color: var(--color-bg);
    font-size: 14px;
    line-height: 1;
    padding: 0 4px;
}
.card__status {
    outline: none;
    border: none;
    cursor: pointer;
    position: absolute;
    left: 50%;
    bottom: 21px;
    z-index: 2;
    transform: translateX(-50%);
    background-color: var(--color-bg);
    font-size: 14px;
    font-weight: 700;
    line-height: 1;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    padding: 0 4px;
    transition: color 0.3s ease-in-out;
}
.card__status:hover,
.card__status:focus {
    color: var(--color-primary-hover);
}
.card__word {
    text-align: center;
    font-size: 18px;
    padding: 56px 38px;
}

.card__status__icon {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    top: 4px;
    width: 48px;
    height: 48px;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: var(--color-bg);
    z-index: 2;
}
.card__status__icon svg {
    width: 100%;
    height: 100%;
    fill: currentColor;
    object-fit: contain;
    object-position: center;
}

.card__btns {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    bottom: 17px;
    z-index: 2;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 10px;
    gap: 20px;
    background-color: var(--color-bg);
    max-width: 100px;
}

.card__btncheck {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 24px;
    height: 24px;
    border: none;
    cursor: pointer;
    background-color: var(--color-bg);
    padding: 0;
    transition: transform 0.3s ease-in-out;
}
.card__btncheck svg {
    display: block;
    width: 100%;
    height: 100%;
    fill: currentColor;
    object-fit: contain;
    object-position: center;
}
.card__btncheck:hover,
.card__btncheck:focus {
    transform: scale(1.1);
}
</style>