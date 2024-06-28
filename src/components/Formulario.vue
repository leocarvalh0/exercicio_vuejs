<script setup>
    const props = defineProps(['retornaNum1', 'retornaNum2', 'trocarFiltro'])
</script>
<template>
    <form>
        <input @keyup="props.retornaNum1" type="number">
        <input @keyup="props.retornaNum2" type="number">
        <select @change="props.trocarFiltro">
            <option value="selecione">Selecione</option>
            <option value="somar">Somar</option>
            <option value="subtrair">Subtrair</option>
            <option value="dividir">Dividir</option>
            <option value="multiplicar">Multiplicar</option>
        </select>
    </form>
</template>
<style>
    form {
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    input {
        width: 80px;
        height: 30px;
        margin-right: 16px;
        background-color: black;
        border: none;
        border-bottom: 2px solid orange;
        color: orange;
        text-align: center;
        font-size: 24px;
        padding: 6px;
    }

    select {
        height: 40px;
        padding: 10px;
        background-color: #000;
        color: #fff;
    }
</style>