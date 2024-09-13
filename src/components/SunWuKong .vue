<template>
    <div>
        <h2>{{ name }}</h2>
        <button @click="changeName">切换形态</button>
        <h3>{{ currentForm }}</h3>
        <p>{{ para }}</p>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
const name = ref<string>('孙悟空')
const para = ref<string>('在《西游记》中，孙悟空是一个勇敢无畏、机智聪明的角色，以其强大的能力和不屈的精神著称。')
const currentForm = ref<string>('齐天大圣')

const changeName = () => {
    currentForm.value = currentForm.value !== '齐天大圣' ? '齐天大圣' : '斗战胜佛'
}
</script>

<style scoped>
div {
    background-color: cadetblue;
    box-shadow: 10px 5px 5px gray;
}
button {
    height: 24px;
    width: 66px;
    font-size: 6%;
    background-color: #c85662;
    margin: -1px;
    outline: none;
}
</style>