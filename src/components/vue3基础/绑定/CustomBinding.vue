<template>
    <div>
        <CustomButton :custom-attr="CustomValue"></CustomButton>
    </div>
</template>

<script setup lang="ts">

import { ref } from 'vue'
import CustomButton from './CustomButton.vue';

const CustomValue = ref<string>('我是自定义属性')

</script>

<style scoped>

</style>