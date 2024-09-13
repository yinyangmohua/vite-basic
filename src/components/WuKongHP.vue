<template>
    <div>
        <p>血量：{{ nowHP }}/{{ maxHP }}({{ hpPercentage }}%)</p>
        <meter min="0"  :max="maxHP" :value="nowHP" style="width: 100%;" low="20" high="70" optimum="90"></meter>
        <input v-model="nowHP" type="range" min="0" max="100">
    </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const maxHP = ref<number>(100)
const nowHP = ref<number>(60)

const hpPercentage = computed(() => {
    return nowHP.value / maxHP.value * 100
})
</script>

<style scoped>
</style>