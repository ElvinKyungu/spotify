<script setup>
import { toRefs } from 'vue'
import { RouterLink } from 'vue-router';

const props = defineProps({
    image: String,
    title: String,
    subTitle: String
})
const { image, title, subTitle } = toRefs(props)
</script>

<template>
    <RouterLink to="library">
        <div class="bg-[#111111] group relative p-4 rounded-md m-2 hover:bg-[#252525] cursor-pointer">
            <img class="rounded-md" :src="image" alt="">
            <div 
                class="
                    absolute top-0 left-0 w-full h-full items-center 
                    justify-center flex opacity-0 transition ease-linear duration-300 
                    translate-y-12 
                    translate-x-12
                    group-hover:translate-y-0 
                    group-hover:opacity-100
                    group-hover:visible group-hover:flex
                                    
                "
            >
                <div class="bg-[#40cb09] rounded-full p-4">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6 ">
                        <path fill-rule="evenodd" d="M4.5 5.653c0-1.426 1.529-2.33 2.779-1.643l11.54 6.348c1.295.712 1.295 2.573 0 3.285L7.28 19.991c-1.25.687-2.779-.217-2.779-1.643V5.653z" clip-rule="evenodd" />
                    </svg>                                  
                </div>
            </div>
            <div class="text-white pt-4 font-semibold text-[17px]">{{ title }}</div>
            <div class="text-gray-400 pt-1 pb-3 text-[14px]">{{ subTitle }}</div>
        </div>
    </RouterLink>
</template>
