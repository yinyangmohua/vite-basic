<template>
    <div>
        <h1>装备管理</h1>
        <input v-model="gearL" type="text" placeholder="输入装备名称">
        <button id="add" @click="pushGear(gearL)">添加装备</button>
        <ul>
            <li v-for="gear in gears" style="list-style-type: none; margin: 3px;">
                {{ gear.name }}
                <button class="del" @click="popGear(gear.id)">删除</button>
            </li>
        </ul>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

interface gear {
    id: number,
    name: string
}

const gears = ref<Array<gear>>([])
const gearL = ref<string>('')

const pushGear = (name: string) => {
    var id =  gears.value.length + 1;
    gears.value.push({id, name})
    gearL.value = ''
}

const popGear = (gear: number) => {
    gears.value = gears.value.filter(e => e.id !== gear);
}
</script>

<style scoped>
input {
    height: 2rem;
    width: 16rem;
    padding: 0.5rem;
    font-size: 1.5rem;
    margin-right: 0.5rem;
    border-radius: 5px;
}
#add {
    width: 8.5rem;
    height: 3.5rem;
    font-size: 1.5rem;
    padding: 0.5rem;
    color:#FFF;
    background-color: #1585FF;
}
#add:hover {
    background-color: #0260A0;
}
.del {
    background-color: red;
    margin: auto;
    padding: 5px;
}
</style>