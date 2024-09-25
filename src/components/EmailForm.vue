<template>
    <div>
        <h2>邮件发送</h2>
        <form @submit.prevent="SubmitEvent">
            <label>发送给</label>
            <input type="email" v-model="email.to"/>
            <label>标题</label>
            <input type="text" v-model="email.subject"/>
            <label>内容</label>
            <textarea v-model="email.body"></textarea>
            <button type="submit">发送</button>
        </form>
    </div>
</template>

<script setup lang="ts">
import { reactive } from 'vue';

const email = reactive({
    to: "",
    subject: "",
    body: ""
})

const props = defineProps<{
    email: {
        to: string;
        subject: string;
        body: string;
    }
}>()

const emit = defineEmits<{
    'submit-event':[any]
}>()

const SubmitEvent = () => {
    emit("submit-event", email)
}
</script>

<style scoped>
/* 容器样式 */  
div {  
    width: 1000px;  
    max-width: 600px; /* 限制最大宽度 */  
    margin: 20px auto; /* 居中并添加外边距 */  
    padding: 20px;  
    background-color: #f9f9f9; /* 浅灰色背景 */  
    border-radius: 8px;  
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); /* 阴影效果 */  
}  
  
/* 表单样式 */  
form {  
    display: flex;  
    flex-direction: column;  
    width: 100%;  
}  
  
/* 标签样式 */  
label {  
    margin-bottom: 5px;  
    font-weight: bold;  
}  
  
/* 输入框和文本域样式 */  
input[type="email"],  
input[type="text"],  
textarea {  
    width: 100%;  
    padding: 10px;  
    margin-bottom: 15px;  
    border: 1px solid #ccc;  
    border-radius: 4px;  
    box-sizing: border-box; /* 确保padding和border不会增加元素的总宽度 */  
}  
  
/* 文本域可能需要一些额外的样式来处理高度 */  
textarea {  
    height: 100px; /* 设置默认高度 */  
    resize: vertical; /* 允许垂直调整大小 */  
}  
  
/* 提交按钮样式 */  
button[type="submit"] {  
    width: 100%;  
    padding: 10px;  
    background-color: #5cb85c; /* 绿色背景 */  
    border: none;  
    border-radius: 4px;  
    color: white;  
    font-size: 16px;  
    cursor: pointer;  
    transition: background-color 0.3s; /* 平滑的背景颜色过渡 */  
}  
  
button[type="submit"]:hover {  
    background-color: #4cae4c; /* 鼠标悬停时的深绿色背景 */  
}
</style>