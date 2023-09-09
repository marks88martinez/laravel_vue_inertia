<template lang="">
    <app-layout>
        <template #header>
            <h1 class="text-base font-semibold text-slate-900">Mostrar Producto</h1>
        </template>
        <div class='py-12'>
            <div class="container mx-auto px-4">
       

                <inertia-link
                    :href="route('productos.create')"
                    class="inline-flex items-center rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">
                    <svg class="-ml-0.5 mr-1.5 h-5 w-5" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                    <path fill-rule="evenodd" d="M16.704 4.153a.75.75 0 01.143 1.052l-8 10.5a.75.75 0 01-1.127.075l-4.5-4.5a.75.75 0 011.06-1.06l3.894 3.893 7.48-9.817a.75.75 0 011.05-.143z" clip-rule="evenodd"></path>
                    </svg>
                    Nuevo
                </inertia-link>
                


              <!-- /////////////////////////////////  -->
              <!-- component -->
                <div class="flex flex-col">
                <div class="overflow-x-auto sm:mx-0.5 lg:mx-0.5">
                    <div class="py-2 inline-block min-w-full sm:px-6 lg:px-8">
                    <div class="overflow-hidden">
                        <table class="min-w-full">
                        <thead class="bg-white border-b">
                            <tr>
                            <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4 text-left">
                                #
                            </th>
                            <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4 text-left">
                                Descripcion
                            </th>
                            <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4 text-left">
                                    Precio
                            </th>
                            <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4 text-left">
                                Accion
                            </th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="producto in productos" :key="producto.id">
                            <td class="px-6 py-4 whitespace-nowrap">
                                <div class="flex items-center">
                                <div class="ml-4">
                                <div class="text-sm font-medium">{{ producto.id }}</div>
                                </div>
                                </div>
                            </td>
                            <td class="px-6 py-4 whitespace-nowrap">
                                <div class="flex items-center">
                                <div class="ml-4">
                                <div class="text-sm font-medium">{{ producto.descripcion }}</div>
                                </div>
                                </div>
                            </td>
                            <td class="px-6 py-4 whitespace-nowrap">
                                <div class="text-sm"><span>$ </span>{{ producto.precio }}</div>                    
                            </td>
                            <td class="flex m-2">
                            <inertia-link 
                                :href="route('productos.edit', producto.id)"
                                class="flex-shrink-0 bg-purple-600 text-white text-base font-semibold py-2 px-4 rounded-lg shadow-md hover:bg-purple-700 focus:outline-none focus:ring-2 focus:ring-purple-500 focus:ring-offset-2 focus:ring-offset-purple-200" type="button">
                                Editar
                            </inertia-link>
                            <inertia-link
                                method="delete"
                                :href="route('productos.destroy', producto.id)"
                                class="flex-shrink-0 bg-pink-500 text-white text-base font-semibold py-2 px-4 rounded-lg shadow-md hover:bg-pink-700 focus:outline-none focus:ring-2 focus:ring-pink-500 focus:ring-offset-2 focus:ring-offset-pink-200" type="button">
                                Borrar
                            </inertia-link>
                            </td>
                        </tr>   
                          
                        </tbody>
                        </table>
                    </div>
                    </div>
                </div>
                </div>
              <!-- /////////////////////////////////  -->
            </div>
            
        </div>
    </app-layout>
        
   
</template>
<script>
import { InertiaLink } from '@inertiajs/inertia-vue3';
import AppLayout from '@/Layouts/AppLayout.vue';


export default {
    props:{
        productos: Array
    },
    components:{

        AppLayout,
        InertiaLink
       
    }
    
}
</script>
<style lang="">
    
</style>