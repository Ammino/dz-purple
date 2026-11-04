<script setup>
    import Button from './Button.vue';
    import IconLocation from '../icons/IconLocation.vue';

    // const emit = defineEmits({
    //     selectCity: {
    //         type: String,
    //         required: true
    //     }
    // });

    //* проверка типа данных, которые передаются в компонент
    const emit = defineEmits({
        selectCity(payload) {
            console.log(`Validation payload: ${payload}`);
            return payload;
        }
    });

    //* вызов события
    const select = () => {
        emit('selectCity', 'Москва');
    }
</script>

<template>
    <div class="city-select">
        <Button @click="select()">
            <template #icon><IconLocation /></template>
            Изменить город
        </Button>
        <div class="city-select__form">
            <input 
                type="text" 
                class="city-select__input" 
                placeholder="Выберите город" />
            <Button>
                Сохранить
            </Button>
        </div>
    </div>
</template>

<style scoped>
    .city-select__form {
        display: flex;
        align-items: center;
        gap: 10px;
    }
    .city-select__input {
        width: 100%;
        padding: 10px;
        border: 1px solid #ccc;
        border-radius: 5px;
    }
</style>