<template>
    <div>
        <button @click="increment(5)">增加5
            <p>当前计数: {{ count }}</p>
        </button>
    </div>
</template>

<script setup lang="ts">

import { ref } from 'vue';

const count = ref<number>(0)

const increment = (value: number): void => {
    count.value += value
}
</script>

<style scoped>

</style>