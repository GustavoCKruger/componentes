<script setup>
import { computed, ref } from 'vue';

const showContent = ref(false);
const buttonText = computed(() =>
    showContent.value ? 'Esconder' : 'Mostrar')
</script>

<template>
    <div>
        <button @click="showContent = !showContent">{{ buttonText }}</button>
        <div v-if="showContent" class="expand-box">
            Aqui vai um texto escondido
        </div>
    </div>
</template>

<style scoped>
.expand-box {
    height: 100%;
    padding: 20px;
    border: 1px solid black;
    box-shadow: 2px 2px 3px 3px gray;
    border-radius: 10px;
}
</style>