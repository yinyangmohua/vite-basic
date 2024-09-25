<template>
  <el-container class="container">
    <el-backtop :right="100" :bottom="100" />
    <el-header style="padding: 0">
      <el-menu
        ellipsis
        class="el-menu"
        mode="horizontal"
        :popper-offset="16"
        style="max-width: 100%"
      >
        <el-menu-item index="1">MLP中文WIKI</el-menu-item>
        <el-sub-menu index="2">
          <template #title>小马相关</template>
          <el-menu-item index="2-1">角色</el-menu-item>
          <el-menu-item index="2-2">小马列表</el-menu-item>
          <el-menu-item index="2-3">家庭与亲属</el-menu-item>
          <el-menu-item index="2-4">家庭与亲属</el-menu-item>
          <el-menu-item index="2-5">背景小马</el-menu-item>
          <el-menu-item index="2-6">陆马</el-menu-item>
          <el-menu-item index="2-7">天马</el-menu-item>
          <el-menu-item index="2-8">独角兽</el-menu-item>
          <el-menu-item index="2-9">可爱标记</el-menu-item>
        </el-sub-menu>
        <el-sub-menu index="3">
          <template #title>电视剧集</template>
          <el-menu-item index="3-1">友谊就是魔法</el-menu-item>
        </el-sub-menu>
        <el-sub-menu index="4">
          <template #title>系列作品</template>
          <el-menu-item index="4-1">动画</el-menu-item>
        </el-sub-menu>
        <el-sub-menu index="5">
          <template #title>地点</template>
          <el-menu-item index="4-1">小马国</el-menu-item>
        </el-sub-menu>
        <el-sub-menu index="6">
          <template #title>文化</template>
          <el-menu-item index="4-1">编年史</el-menu-item>
        </el-sub-menu>
      </el-menu>
    </el-header>
    <el-main>
      <el-card style="width: 70%; margin: auto">
        <el-card style="max-width: 680px; margin: auto">
          <template #header>每周推荐</template>
          <img
            src="https://huiji-public.huijistatic.com/mlp/uploads/f/fe/Twilight_singing_%22my_Ponyville%22_S03E13.png"
            style="width: 100%"
          />
        </el-card>
        <el-row :gutter="20" style="margin: 2rem">
          <el-col :span="4"
            ><el-button class="button" plain>角色导航</el-button></el-col
          >
          <el-col :span="4"
            ><el-button class="button" plain>剧集导航</el-button></el-col
          >
          <el-col :span="4"
            ><el-button class="button" plain>地点导航</el-button></el-col
          >
          <el-col :span="4"
            ><el-button class="button" plain>系列作品</el-button></el-col
          >
          <el-col :span="4"
            ><el-button class="button" plain>社会文化</el-button></el-col
          >
          <el-col :span="4"
            ><el-button class="button" plain>站点索引</el-button></el-col
          >
        </el-row>
        <div style="display: flex; justify-content: center">
          <el-card style="width: 440px; margin: auto">
            <template #header>统计信息</template>
            <el-progress
            class="progress"
              :text-inside="true"
              :stroke-width="20"
              :percentage="42.7"
              status="exception"
            >
              <span>填坑进度：1397m/3274m (42.7%)</span>
            </el-progress>
            <el-progress
            class="progress"
              :text-inside="true"
              :stroke-width="20"
              :percentage="93.1"
              status="success"
            >
              <span>1500个内容页面：93.1%</span>
            </el-progress>
            <el-progress
            class="progress"
              :text-inside="true"
              :stroke-width="20"
              :percentage="92.9"
              status="warning"
            >
              <span>70000次编辑：92.9%</span>
            </el-progress>
          </el-card>
          <el-card style="width: 440px; margin: auto">
            <template #header>响应号召</template>
            <p>加入维基编辑！为马国效力！</p>
            <p>编辑QQ群 ：180954392</p>
          </el-card>
        </div>
      </el-card>
    </el-main>
  </el-container>
</template>

<script setup lang="ts"></script>

<style scoped>
.container {
  height: 100vh;
  background-color: #79bbff;
}
.button {
  height: 3rem;
  width: 8rem;
  font-size: 1rem;
  font-weight: bold;
}
.progress {
    margin: 10px;
}
span {
    color: #000000aa;
}
</style>
