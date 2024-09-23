<script setup>
const props = defineProps(['num1', 'num2', 'filtro'])
</script>

<template>
    <form>
        <div class="row align-items-center">
            <div class="col-md-3">
                <input class="form-control" @keyup="props.num1" type="number">
            </div>
            <div class="col-md-3">
                <input class="form-control" @keyup="props.num2" type="number">
            </div>
            <div class="col-md-6">
                <select @change="props.filtro" class="form-control text-center">
                    <option value="Adição">Adição</option>
                    <option value="Subtração">Subtração</option>
                    <option value="Multiplicação">Multiplicação</option>
                    <option value="Divisão">Divisão</option>
                </select>
            </div>
        </div>
    </form>

</template>