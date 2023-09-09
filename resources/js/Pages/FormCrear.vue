<template lang="">
      <app-layout>
        <template #header>
            <h1 class="text-base font-semibold text-slate-900">Crear Producto</h1>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg">
                    
                <form @submit.prevent="submit" class="mb-6">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-5 md:gap-8 mt-5 mx-7">
                
                <div class="grid grid-cols-1">
                    <label class="uppercase md:text-sm text-xs text-gray-500 text-light font-semibold">Descripción</label>
                    <input 
                    id="descripcion"
                    v-model="form.descripcion"
                    class="py-2 px-3 rounded-lg border-2 border-purple-300 mt-1 focus:outline-none focus:ring-2 focus:ring-purple-600 focus:border-transparent" type="text" placeholder="Descripción" 
                    />
                </div>
                
                <div class="grid grid-cols-1">
                    <label class="uppercase md:text-sm text-xs text-gray-500 text-light font-semibold">Precio</label>
                    <input         
                        id="precio"
                        v-model="form.precio"                
                    class="py-2 px-3 rounded-lg border-2 border-purple-300 mt-1 focus:outline-none focus:ring-2 focus:ring-purple-600 focus:border-transparent" type="text" placeholder="Precio" 
                    />
                </div>
                </div>
            
            
                <div class='flex justify-end md:gap-8 gap-4 pt-5 pb-5 pr-5'>      
                <inertia-link
                    :href="route('productos.index')"                    
                    class='w-auto bg-gray-500 hover:bg-gray-700 rounded-lg shadow-xl font-medium text-white px-4 py-2' type="button">
                    Cancelar
                </inertia-link> 
                <button 
                    type="submit"
                    class='w-auto bg-purple-500 hover:bg-purple-700 rounded-lg shadow-xl font-medium text-white px-4 py-2'
                >
                    Guardar
                </button>
                </div>
            
                </form>
										
                </div>
            </div>
        </div>
       
    </app-layout>
        
</template>
<script>
import { InertiaLink } from '@inertiajs/inertia-vue3';
import AppLayout from '@/Layouts/AppLayout.vue';
export default {
    data() {
        return {
            form:{
                descripcion: null,
                precio: null,
            },
            
        }
    },
    components:{
        InertiaLink
    },
    props:{
        errors: Object
    },
    methods: {
        submit(){
           this.$inertia.post(route('productos.store'),this.form); 
        }
    },
    components:{
        AppLayout

        }   
}
</script>
<style lang="">
    
</style>