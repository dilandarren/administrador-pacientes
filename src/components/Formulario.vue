<template>
    <div class="md:w-1/2">
        <h2 class="font-black text-3xl text-center">Seguimiento Pacientes</h2>

        <p class="text mt-5 text-center mb-10">
            Añade Pacientes y
            <span class="text-indigo-600 font-bold">Adminístralos</span>
        </p>

        

        <form
            class="bg-white shadow-lg rouded-lg py-10 px-5 mb-10"
            @submit.prevent="validar"
        >

            {{ nombre }}
        
        <!-- Begin Input -->
        <div class="mb-5">
            <label 
                for="mascota"
                class="block text-gray700 uppercase font-bold"
            >

                Nombre mascota
            </label>

            <input 
                id="mascota"
                type="text"
                placeholder="Nombre de la mascota"
                class="border-2 w-full p-2 mt-2 placeholder:gray-400 rounded-md"
                @input="$emit('update:nombre', $event.target.value)"
                
            >
        </div>
        <!-- End Input -->



        <!-- Begin Input -->
        <div class="mb-5">
            <label 
                for="propietario"
                class="block text-gray700 uppercase font-bold"
            >
                Nombre Propietario
            </label>

            <input 
                id="propietario"
                type="text"
                placeholder="Nombre del Propietario"
                class="border-2 w-full p-2 mt-2 placeholder:gray-400 rounded-md"
                
            >
        </div>
        <!-- End Input -->



        <!-- Begin Input -->
        <div class="mb-5">
            <label 
                for="email"
                class="block text-gray700 uppercase font-bold"
            >
                Email
            </label>

            <input 
                id="email"
                type="email"
                placeholder="Email del Propietarios"
                class="border-2 w-full p-2 mt-2 placeholder:gray-400 rounded-md"
                
            >
        </div>
        <!-- End Input -->


        <!-- Begin Input -->
        <div class="mb-5">
            <label 
                for="alta"
                class="block text-gray700 uppercase font-bold"
            >
                Alta
            </label>

            <input 
                id="alta"
                type="date"
                class="border-2 w-full p-2 mt-2 placeholder:gray-400 rounded-md"
                
            >
        </div>
        <!-- End Input -->

        <!-- Begin Input -->
        <div class="mb-5">
            <label 
                for="sintomas"
                class="block text-gray700 uppercase font-bold"
            >
                Síntomas
            </label>

            <textarea 
                id="alta"
                placeholder="Describe los síntomas"
                class="border-2 w-full p-2 mt-2 placeholder:gray-400 rounded-md h-40"
                
            />
        </div>

        <input 
            type="submit"
            class="text-center rounded-lg bg-indigo-600 w-full p-3 text-white uppercase foont-bold hover:bg-indigo-700 cursor-pointer transition-colors"
            value="Registrar Paciente"
        >
        <!-- End Input -->
         <div
            class="mt-5"
         >
            <Alerta
                v-if="alerta.mensaje"
                :alerta="alerta"
            />
         </div>

        </form>
    </div>
</template>

<script setup>

import { reactive } from 'vue';
import Alerta from './Alerta.vue';

const alerta = reactive({
    tipo: '',
    mensaje: ''
})


defineEmits(['update:nombre'])

const props = defineProps({
    nombre: {
        type: String,
        required: true
    }
})


const validar = () => {

    if (Object.values(paciente).includes('')) {
        alerta.mensaje = 'Todos los campos son obligatorios'
        alerta.tipo = 'error'
        return
    }

    console.log('Agregando');

    
}

</script>
