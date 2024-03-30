<template>
    <div>
        <h6 class="text-[#d7242d] font-medium text-sm">{{ author }}</h6>
        <h1 class="font-bold text-2xl mb-4">{{ title }}</h1>
        <h2 class="mb-4 text-sm">{{ body }}</h2>
        <a href="" class="uppercase border-b-2 border-black font-bold text-xs py-1 hover:border-[#d7242d]">Read
            Article</a>
    </div>
</template>

<script setup>
// Receive the props passed
const props = defineProps({
    author: String,
    title: String,
    body: String,
})
</script>
