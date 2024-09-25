<template>
  <div>
    <EmailForm :email @submit-event="handleSubmit" />
    <p v-if="submitData">子组件提交的表单数据是: {{ submitData }}</p>
  </div>
</template>

<script setup lang="ts">
import { ref, reactive } from "vue";
import EmailForm from "./EmailForm.vue";
import axios from "axios";

const email = reactive({
  to: "",
  subject: "",
  body: "",
});

const submitData = ref(null);

const handleSubmit = (data: any) => {
  submitData.value = data;
  axios.post("http://localhost:8080/mail", submitData.value)
  .then((res) => {
    console.log(res.data)
  })
  .catch(e => { console.log(e) })
};
</script>

<style scoped></style>
