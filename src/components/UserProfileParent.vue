<template>
    <div>
        <!-- 传递user对象给子组件-->
        <UserProfile :user="myUser"/>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import UserProfile from './UserProfile.vue';

const myUser = ref({
    name: "张三",
    age: 20,
    email: "c@qq.com"
})
</script>

<style scoped>

</style>