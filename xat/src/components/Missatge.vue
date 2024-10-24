<script setup>
import { ref } from 'vue';

const props = defineProps({
    userFill: String
})
const emits=defineEmits(['enviarMisatge'])
const nouMisatge=ref('')
const enviarMisatge=()=>{
    emits('enviarMisatge', nouMisatge.value)
}
</script>

<template>
    <input type="text" v-model="nouMisatge" placeholder="Escriu un missatge">
    <input type="button" value="Enviar missatge" @click="enviarMisatge">
</template>