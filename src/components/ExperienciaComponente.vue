<script setup>
import icono1 from '../assets/favicon.ico';
import icono2 from '../assets/favicon.ico';
import icono3 from '../assets/favicon.ico';
import icono4 from '../assets/favicon.ico';


import {ref} from 'vue';
const titulo='Gestion de sueldos';
const fecha='2020 - Actualidad';
const experiencias = ref([
    {id:1, src: icono1, parrafo: 'Gestion de cuentas corrientes.'},
    {id:2, src: icono2, parrafo: 'Gestión de sueldos.'},
    {id:3, src: icono3, parrafo: 'Experiencia en sofware de gestion.'},
    {id:4, src: icono4, parrafo: 'Control de empleados.'}
    
]);
</script>

<template>
    <div class="card">
        <h3 class="titulo">{{titulo.toLocaleUpperCase()}}</h3>
        <p class="fecha">{{fecha}}</p>
        <ul class="listado">
            <li class="item" v-for="experiencia in experiencias" :key="experiencia.id">
                <img class="imagen-svg" :src="experiencia.src" width="20px" :alt="experiencia.parrafo">
                <p>{{experiencia.parrafo}}</p>
            </li>
            
        </ul>
    </div>
</template>

<style scoped>
.card{
    display: flex;
    flex-direction: column;
    padding:2rem;
    background-color: rgb(132, 0, 255);
    border-radius: 15px;
}
.titulo{
    font-size:1.5rem;
    color: rgb(255, 187, 0);
}
.fecha{
    font-size: 1rem;
    color: rgb(255, 0, 0);
    margin-bottom: 1rem;
}
.listado{
    display: flex;
    flex-direction: column;
}
.item{
    align-items: center;
    display: flex;
    padding: 1rem;
    gap: 1.5rem;
}
</style>
