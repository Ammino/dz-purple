<script setup>
    import Stat from './components/Stat.vue';
    import CitySelect from './components/CitySelect.vue';

    const data = {
        label: "Влажность",
        value: "60%",
    };

    function getCity(city) {
        console.log(city);
    }
</script>

<template>
    <main>
        <section class="block__padd">
            <div class="container">
                <div class="weather">
                    <div class="weather__leftpanel">
                    </div>
                    <div class="weather__body">
                        <Stat :label="data.label" :value="data.value" />
                        <Stat :="data" />
                        <Stat :label="data.label" :value="data.value" />
                    </div>
                    <CitySelect @select-city="getCity" />
                </div>
            </div>
        </section>
    </main>
</template>

<style scoped>
  .weather {
    max-width: 944px;
    padding: 60px 48px 60px calc(50% - 48px);
    background: var(--color-bg-card);
    border-radius: 25px;
    margin: 0 auto;
  }
</style>