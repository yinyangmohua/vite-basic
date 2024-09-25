<template>
  <div class="common-layout">
    <el-container>
      <el-header>
        <el-menu
          :default-active="activeIndex"
          class="el-menu-demo"
          mode="horizontal"
          :ellipsis="false"
          @select="handleSelect"
        >
          <el-menu-item index="0">
            <scan style="font-size: large">力扣</scan>
          </el-menu-item>
          <el-menu-item index="1">学习</el-menu-item>
          <el-menu-item index="2">题库</el-menu-item>
          <el-menu-item index="3">竞赛</el-menu-item>
          <el-menu-item index="4">讨论</el-menu-item>
          <el-sub-menu index="5">
            <template #title>商店</template>
            <el-menu-item index="2-1">精品商店</el-menu-item>
            <el-menu-item index="2-2">力扣周边</el-menu-item>
            <el-menu-item index="2-3">plus会员</el-menu-item>
          </el-sub-menu>
        </el-menu>
      </el-header>
      <el-container>
        <el-aside width="400px">
          <el-calendar
            class="test"
            v-model="value"
            style="width: 400px; height: 200px"
          />
        </el-aside>
        <el-main>
          <el-text class="mx-1" size="large" style="font-weight: bold"
            >推荐</el-text
          >
          <el-carousel :interval="4000" type="card" height="200px">
            <el-carousel-item
              v-for="(item, index) in items"
              :key="index"
              style="width: auto"
            >
              <h3 text="2xl" justify="center">
                <img :src="item" style="max-height: 200px" />
              </h3>
            </el-carousel-item>
          </el-carousel>
          <el-text class="mx-1" size="large" style="font-weight: bold"
            >学习计划</el-text
          >
          <el-row :gutter="25" v-for="ccard in cards" style="margin: auto">
            <el-col :span="7" v-for="rcard in ccard"
              ><el-card style="margin: 1rem 0">
                <div style="display: flex">
                  <img :src="rcard.img" style="max-height: 60px" />
                  <p style="margin: auto">{{ rcard.text }}</p>
                </div>
              </el-card></el-col
            >
          </el-row>
          <div class="flex gap-2" style="display: flex">
            <div v-for="tag in list" style="margin: 1rem">
              <el-check-tag checked type="info">{{ tag }}</el-check-tag>
            </div>
          </div>
          <el-table :data="tableData" stripe style="width: 100%">
            <el-table-column prop="title" label="题目" width="280" />
            <el-table-column prop="out" label="题解" width="180" />
            <el-table-column prop="run" label="通过率" width="180"/>
            <el-table-column prop="e" label="难度"/>
          </el-table>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

interface card {
  img: string;
  text: string;
}
const activeIndex = ref("1");
const handleSelect = (key: string, keyPath: string[]) => {
  console.log(key, keyPath);
};
const value = ref(new Date());
const items = ref<string[]>([
  "https://pic.leetcode.cn/1681889436-PUCPnR-%E9%A2%98%E5%BA%93.png?x-oss-process=image%2Fformat%2Cwebp",
  "https://pic.leetcode.cn/1680175999-ZPMKSx-%E9%A2%98%E5%BA%93%20(1).png?x-oss-process=image%2Fformat%2Cwebp",
  "https://pic.leetcode.cn/1671678041-lXzrOx-%E5%A4%A7%E8%AF%9D%E5%B9%B6%E5%8F%91-%E9%A2%98%E5%BA%93.jpg?x-oss-process=image%2Fformat%2Cwebp",
  "https://pic.leetcode.cn/1683280468-quwfIB-%E9%A2%98%E5%BA%93.png?x-oss-process=image%2Fformat%2Cwebp",
  "https://pic.leetcode.cn/1672051517-bpQKao-%E7%AE%97%E6%B3%95%E8%AE%AD%E7%BB%83%E8%90%A5.png?x-oss-process=image%2Fformat%2Cwebp",
  "https://pic.leetcode-cn.com/1631072932-aldbWv-%E5%B9%B6%E6%9F%A5%E9%9B%86.jpg?x-oss-process=image%2Fformat%2Cwebp",
]);
const cards = ref<card[][]>([
  [
    {
      img: "https://assets.leetcode.cn/aliyun-lc-upload/study_plan_v2/top-interview-150/cover",
      text: "面试经典150题",
    },
    {
      img: "https://assets.leetcode.cn/aliyun-lc-upload/study_plan_v2/dynamic-programming/cover",
      text: "动态规划（基础版）",
    },
    {
      img: "https://assets.leetcode.cn/aliyun-lc-upload/study_plan_v2/top-100-liked/cover",
      text: "热题100",
    },
  ],
  [
    {
      img: "https://assets.leetcode.cn/aliyun-lc-upload/study_plan_v2/sql-premium-50/cover",
      text: "高频SQL 50题",
    },
  ],
]);

const list = ref<string[]>([
  "全部题目",
  "算法",
  "数据库",
  "Shell",
  "多线程",
  "JavaScript",
  "pandas",
]);

const tableData = [
  {
    title: "公司命名",
    out: "77",
    run: "50.2%",
    e: "困难"
  },
  {
    title: "两数之和",
    out: "25675",
    run: "54.2%",
    e: "简单"
  },
  {
    title: "两数相加",
    out: "14541",
    run: "50.1%",
    e: "中等"
  },
];
</script>

<style scoped>
.el-menu--horizontal > .el-menu-item:nth-child(1) {
  margin-right: auto;
}

.test /deep/ .el-calendar-table .el-calendar-day {
  width: 60px;
  height: 40px;
}

.el-carousel__item h3 {
  color: #475669;
  opacity: 0.75;
  line-height: 200px;
  margin: 0;
  text-align: center;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
  background-color: #d3dce6;
}
.el-row {
  margin-bottom: 20px;
}
.el-row:last-child {
  margin-bottom: 0;
}
.el-col {
  border-radius: 4px;
}

.grid-content {
  border-radius: 4px;
  min-height: 36px;
}
</style>
