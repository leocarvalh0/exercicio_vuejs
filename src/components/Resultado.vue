<script setup>
    const props = defineProps(['trocarFiltro', 'filtro'])
</script>

<template>
    <p v-if="props.filtro == 'selecione'">Selecione um operador</p>
    <p v-else>Resultado: <span>{{ props.trocarFiltro }}</span></p>
</template>

<style>
    p {
        font-size: 24px;
        margin-top: 60px;
    }

    span {
        color: orange;
        font-weight: bold;
    }
</style>