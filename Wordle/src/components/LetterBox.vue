<template>
    <div class="col-span-1 flex items-center justify-center h-16 uppercase border-2 border-gray-200">
    {{ letter }}
    </div>
</template>
<script setup>
const props = defineProps({
    letter : {
        type: String,
        default: '',
    }
}) 
</script>
    