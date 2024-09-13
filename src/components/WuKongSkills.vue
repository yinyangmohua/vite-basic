<template>
    <div>
        <h2>孙悟空 技能列表</h2>
        <ul style="list-style-type: none;">
            <li v-for="skill in skills" :key="skill.id">
                {{ skill.name }}
                <span> - </span>
                <span v-if="skill.unlock" style="color: greenyellow;">已解锁</span>
                <span v-else style="color: brown;">未解锁</span>
            </li>
        </ul>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
interface skills {
    id: number,
    name: string,
    unlock: boolean
}
const skills = ref<skills[]>([
    {id: 1, name: '火眼金睛', unlock: true},
    {id: 2, name: '筋斗云', unlock: true},
    {id: 3, name: '七十二变', unlock: false},
])
</script>

<style scoped>

</style>