<template>
    <div>
        <input ref="inputElement" type="text" placeholder="聚焦在此"/>
        <button type="button" @click="focusInput()">点击聚焦输入框</button>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const InputElement = ref<HTMLInputElement | null>(null)

const focusInput = () => {
    if(InputElement.value) {
        InputElement.value.focus()
    }
}
</script>

<style scoped>

</style>