<script setup>
import { computed, ref } from 'vue';

//const props = defineProps(['title', 'content']);
defineProps({
    title: {
        type: String,
        required: true
    },
    content: {
        type: String,
        default: 'Valor padrão do texto da caixa'
    },
    quantity: {
        type: Number,
        default: 10
    }
})

const showContent = ref(false);
const buttonText = computed(() =>
    showContent.value ? 'Esconder' : 'Mostrar',
);
</script>

<template>
    <div>

        <button @click="showContent = !showContent">{{ buttonText }}</button>
        <div v-if="showContent" class="expand-box">
            <h1>{{ title }}</h1>
            <p>{{ content }}</p>
            <p>{{ quantity }}</p>
        </div>

    </div>
</template>

<style scoped>
.expand-box {
    height: 100%;
    padding: 20px;
    border: 1px solid gray;
    border-radius: 5px;
    box-shadow: 3px 3px 2px 2px gray;
}
</style>