<script setup>
import { computed } from 'vue';

const props = defineProps({
    type: String,
    title: String,
    description: String
});

const image = computed(() => {
    switch(props.type) {
        case "1": 
            return new URL('../assets/buryam.png', import.meta.url).href;
        case "2":
            return new URL('../assets/ayam.png', import.meta.url).href;
        case "3":
            return new URL('../assets/babi.png', import.meta.url).href;
        case "4":
            return new URL('../assets/tuna.png', import.meta.url).href;
        default:
            return new URL('../assets/ayam.png', import.meta.url).href;
    }
});
</script>


<template>
    <div id="barang" class="w-full flex-1 h-52 p-5 overflow-hidden rounded-md bg-white shadow-lg relative flex">
        <img :src="image" class="w-full h-full absolute inset-0 object-cover"/>
        <div class="w-full h-full absolute  inset-0 bg-gradient-to-t from-neutral-900 to-transparent"></div>
        <div class="text-white self-end">
            <h1 class="text-lg relative font-semibold z-50">{{ props.title }}</h1>
            <p class="z-50 text-xs text-justify font-thin relative">{{ props.description }}</p>
        </div>
    </div>
</template>
