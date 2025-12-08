<template>
  <div class="membership-blocks">
    <h2 class="title">Разовые тренировки</h2>
    <div class="blocks">
        <div class="block">
            <h1>Самостоятельные тренировки<br>в тренажерном зале</h1>
            <span style="text-align: center; color: var(--color-grey);">8:00 – 23:00</span>
            <img src="/images/clock.png"/>
            <span style="font-size: 20px; font-weight: 900;">250₽</span>
            <span style="text-align: center; color: var(--color-grey);">1 тренировка</span>
            <Button variant="custom">Узнать</Button>
        </div>
        <div class="block">
            <h1>Персональный тренинг<br>с инструктором</h1>
            <span style="text-align: center; color: var(--color-grey);">8:00 – 23:00</span>
            <img src="/images/clock.png"/>
            <span style="font-size: 20px; font-weight: bolder;">700₽</span>
            <span style="text-align: center; color: var(--color-grey);">1 тренировка</span>
            <Button variant="custom">Узнать</Button>
        </div>
        <div class="block">
            <h1>Зал групповых<br>программ</h1>
            <span style="text-align: center; color: var(--color-grey);">8:00 – 23:00</span>
            <img src="/images/clock.png"/>
            <span style="font-size: 20px; font-weight: bolder;">300₽</span>
            <span style="text-align: center; color: var(--color-grey);">график у администратора</span>
            <Button variant="custom">Узнать</Button>
        </div>
    </div>
  </div>
</template>

<script setup>
    import Button from '../../../Button.vue';
</script>

<style scoped>
    .title {
        text-align: center;
        font-size: 25px;
        font-weight: bold;
        height: 100px;
    }
    .membership-blocks {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 50px;
        padding-top: 50px;
    }
    .blocks {
        display: flex;
        flex-direction: row;
        align-items: center;
        gap: 30px;
    }
    .block {
        display: flex;
        flex-direction: column;
        align-items: center;
        min-width: 250px;
        min-height: 320px;
        gap: 20px;
        padding: 20px;
        box-shadow: -4px 4px 10px rgba(0,0,0,0.25);

        > h1 {
            font-weight: 900;
            text-align: center;
        }
    }
</style>