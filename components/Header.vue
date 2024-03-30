<template>
    <div class="space-y-[-2.2rem]">
        <!-- Image header -->
        <div class="relative w-full h-96 overflow-hidden">
            <img :src="path + imageUrl" class="absolute inset-0 w-full h-full object-cover object-center" />
        </div>
        <!-- Date -->
        <div
            class="ml-8 w-max h-max bg-[#d7242d] transform skew-x-[-8deg] text-center items-center justify-center py-2 px-5 space-y-[-0.4rem]">
            <h1 class="text-white items-center justify-center text-xl font-semibold">{{ day }}</h1>
            <h2 class="text-white items-center justify-center text-[0.6rem]">{{ month }}</h2>
        </div>
    </div>
</template>

<script setup>
// Declare the image path to concat it to the image_url from the JSON file provided
const path = '/_nuxt/assets/image/';

// Receive the props passed
const props = defineProps({
    imageUrl: String,
    day: Date,
    month: Date
})
</script>
