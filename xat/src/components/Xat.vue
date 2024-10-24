<script setup>
import { ref } from 'vue';
import Missatge from './Missatge.vue';
const user="Kameron"
const llistaMissatges=ref([])
const gestionarMisatge=(nouMisatge)=>{
    llistaMissatges.value.push({
        id:Date.now(),
        usuari:user,
        contingut:nouMisatge
    })
}

</script>

<template>
    <main>
        <div>
            <h2>Xat entre users</h2>
            <ul>
                <li v-for="missatge in llistaMissatges" :key="missatge.id">{{ missatge.usuari }} : {{ missatge.contingut }}</li>
            </ul>
            <Missatge :userFill=user @enviarMisatge="gestionarMisatge"></Missatge>
            
        </div>
    </main>


</template>