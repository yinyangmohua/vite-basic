<template>
    <div>
        <button :disabled="isDisabled">点击我</button>
        <button v-bind="buttonattrs">点击我</button>
        <img :src="url"/>
    </div>
</template>

<script setup lang="ts">

import { ref } from 'vue'
import { reactive } from 'vue';

const isDisabled = ref<boolean>(false)
const buttonattrs = reactive({
    disabled: false,
    title: '按钮已禁用',
    id: 'unique-button'
})
const url = ref<string>(
    'https://img-s-msn-com.akamaized.net/tenant/amp/entityid/AA1pXTuX.img?w=532&h=780&m=6'
)

</script>