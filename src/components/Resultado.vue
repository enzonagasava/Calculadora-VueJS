<script setup>
    const props = defineProps(['resultado'])
</script>

<template>
    <div class="row align-items-center">
        <div class="p-5 mt-4 mb-4 bg-light rounded-3 border border-dark">
            <p class='fs-2 mt-3 text-center '>Resultado: {{ props.resultado }}</p>
        </div>
    </div>

</template>