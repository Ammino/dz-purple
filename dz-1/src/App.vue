<script setup>
    import Button from './components/Button.vue';
</script>

<template>
    <main>
        <section class="block__padd">
            <div class="container">
                <div class="weather">
                    <div class="weather__leftpanel">
                    </div>
                    <div class="weather__body">
                        <Button>
                            <template #icon>+</template>
                            Сохранить
                        </Button>
                    </div>
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