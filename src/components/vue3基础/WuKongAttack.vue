<template>
    <div>
        <p>基础攻击力：{{ baseAttack }}</p>
        <p>装备攻击力: {{ gearBonus }}</p>
        <p>buff等级: {{ strength }}</p>
        <p>总攻击力: {{ totalAttack }}</p>
    </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const baseAttack = ref<number>(100)
const gearBonus = ref<number>(0)
const strength = ref<number>(0)

const totalAttack = computed(() => {
    return (baseAttack.value + gearBonus.value) * (1 + (strength.value * 0.2))
})
</script>

<style scoped>

</style>