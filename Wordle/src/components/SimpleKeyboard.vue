<template>
    <div class="simple-keyboard"></div>
</template>
<script setup>
import Keyboard from "simple-keyboard";
import 'simple-keyboard/build/css/index.css';
import { ref,onMounted } from "vue";
const keyboard = ref(null);
const emit = defineEmits(['onKeyPress'])

const onKeyPress = (button)=>{
    emit("onKeyPress",button)
}
onMounted(()=>{
    keyboard.value = new Keyboard('simple-keyboard',{
    layout: {
        default: [
            "a z e r t y u i o p",
            "q s d f g h j k l m",
            "{enter} w x c v b n {bksp}",
        ],
    },
    onKeyPress: onKeyPress
});
})
</script>