<template>
    <div>
        <input v-model.lazy.trim="name" placeholder="请输入姓名" />
        <p>您输入的姓名是: {{ name }}</p>
        <input v-model.number="age" type="number" placeholder="请输入年龄" />
        <p>您的年龄是: {{ age }}</p>
    </div>
</template>

<script setup lang="ts">

import { ref } from 'vue';

const name = ref<string>('')
const age = ref<number | null>(null)
</script>

<style scoped>

</style>