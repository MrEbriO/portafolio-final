<script setup>
import img1 from '/src/components/icons/javascript.svg';
import img2 from '/src/components/icons/java.svg';
import img3 from '/src/components/icons/python.svg';
import img4 from '/src/components/icons/vsc.svg';
import img5 from '/src/components/icons/git.svg';
import img6 from '/src/components/icons/office.svg';
import img7 from '/src/components/icons/arg.svg';
import img8 from '/src/components/icons/eeuu.svg';
import {ref} from 'vue';
const habilidades = ref([
    {
        id: 1, nombre: 'Lenguajes de Programación', habilidades: [
            {id: 1, nombre: 'JavaScript', nivel:'Imtermedio', icono: img1},
            {id: 2, nombre: 'Java', nivel:'Intermedio', icono: img2},
            {id: 3, nombre: 'Python', nivel:'Basico', icono: img3}
        ]
    },
    {
        id: 2, nombre: 'Herramientas y Software', habilidades: [
            {id: 1, nombre: 'Visual Studio Code', nivel:'Intermedio', icono: img4},
            {id: 2, nombre: 'Git', nivel:'Basico', icono: img5},
            {id: 3, nombre: 'Paquete Office', nivel:'Avanzado', icono: img6}
    ]
    },
    {
        id: 3, nombre: 'Idiomas', habilidades: [
            {id: 1, nombre: 'Español', nivel:'Avanzado', icono: img7},
            {id: 2, nombre: 'Ingles', nivel:'Basico', icono: img8}
    ]
    }


])
</script>

<template>
<div class="skills-contenedor">
    <div v-for= "habilidad in habilidades" :key="habilidad.id" class="skills-categoria">
        <h3>{{habilidad.nombre}}</h3>
        <ul class="skills">
            <li v-for="habilidad in habilidad.habilidades" :key="habilidad.id" class="skill">
                <img :src="habilidad.icono" :alt="habilidad.nombre">
                <span>{{habilidad.nombre}}: {{ habilidad.nivel }}</span>
            </li>

        </ul>
    </div>
    <!-- <div class="skills-categoria">
        <h3>Herramientas y Software</h3>
        <ul class="skills">
            <li class="skill">
                <img src="/src/components/icons/vsc.svg" alt="Visual Studio Code">
                <span>Visual Studio Code: Avanzado</span>
            </li>
            <li class="skill">
                <img src="/src/components/icons/git.svg" alt="Git">
                <span>Git: Avanzado</span>
            </li>
            <li class="skill">
                <img src="/src/components/icons/office.svg" alt="Paquete Office">
                <span>Paquete Office: Avanzado</span>
            </li>
        </ul>
    </div>
    <div class="skills-categoria">
        <h3>Idiomas</h3>
        <ul class="skills">
            <li class="skill">
                <img src="/src/components/icons/arg.svg" alt="Español">
                <span>Español: Nativo</span>
            </li>
            <li class="skill">
                <img src="/src/components/icons/eeuu.svg" alt="Ingles">
                <span>Ingles: Besico</span>
            </li>
        </ul>
    </div> -->
</div>
</template>

<style scopped>
.skills-contenedor{
    padding: 2rem;
    background-color: rgb(28, 41, 52);
}
.skills-categoria{
    margin-bottom: 20px;
}
.skills-categoria h3{
    display: flex;
    justify-content:left;
    margin-bottom: 10px;
    font-size: 1.5em;
    color: aliceblue;
    font-size: 1.5em;
    font-weight: bold;
}
.skills{
    display: flex;
    justify-content: space-evenly;
    flex-wrap: wrap;
    gap: 20px;
}
.skill{
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
    background-color: rgba(255, 255, 255, 0.856);
    padding: 0.3em;
    border-radius:8px;
    box-shadow: 0px 4px 12px rgba(162, 0, 255, 0.963);
    flex: 1 1 200px;
    max-width: 250px;
}
.skill:hover{
    background-color: rgba(0, 255, 255, 0.963);
}
.skill img{
    width: 35px;
    height: 35px;
}
.skill span{
    font-size: 1em;
    color: #2600ff;
}
.skill:hover{
    font-size: 1.3em;
    transition: 2s ease;
}
@media (max-width: 768px){
    .skills-categoria h3{
        justify-content: center;
    }
    .skill{
        justify-content: center;
    }
}
</style>