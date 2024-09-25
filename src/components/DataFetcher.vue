<template>
    <div>

    </div>
</template>

<script setup lang="ts">
import { onMounted, onUnmounted, ref } from 'vue';

const data = ref<string | null>(null)
const loading = ref(false);

const fetchData = async () => {
    loading.value = true;
    await new Promise((resolve) => setTimeout(resolve, 2000));
    data.value = '加载完成';
    loading.value = false;
};

//组件挂载的生命周期
onMounted(() => {
    console.log("组件挂载，开始请求数据...");
    fetchData();
})

onUnmounted(() => {
    console.log("组件卸载，清理资源");
})
</script>

<style scoped>

</style>