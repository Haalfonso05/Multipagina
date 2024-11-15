<script setup>
    import {ref} from 'vue'

    let qty = ref(1)

    function add(){
        qty.value++   
        console.log(qty)
    }
    function sustrade(){
        if (qty.value>0){
            qty.value--
        }else{
            console.log('Pero tilin?')
        }
        
        console.log(qty)
    }
</script>
<template>
    <div class="bg-purple-300 rounded max-w-80 mx-auto p-6">
        <div 
            v-if="qty > 0"
            class="bg-red-500 rounded-full text-white size-8 flex justify-center items-center font-bold"
            :class="{'bg-orange-500': qty > 101}"
            
        >
            {{ qty }}
        </div>
        <div v-else>
            Nadie te visita :(
        </div>
        <div class="flex">
            <div
            @click="add"
            class="bg-blue-400 text-white rounded size-6 flex justify-center items-center mr-4 hover:cursor-pointer">
            +
        </div>
        <div
            @click="sustrade"
            class="bg-blue-400 text-white rounded size-6 flex justify-center items-center hover:cursor-pointer">
            -
        </div>
        </div>
        
    </div>
    
</template>