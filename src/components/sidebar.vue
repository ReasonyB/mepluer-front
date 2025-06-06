<script setup>
import { ref } from 'vue';
import SidebarButton from './SidebarButton.vue';
const idex = ref(1);
</script>

<template>
  <div class="sidebar-container" style="display: flex;">
    <div class="sidebar bg">
      <div id="logo"></div>
      <SidebarButton :isActive="idex=='0'">
        <template #title>Tasks</template>
      </SidebarButton>
      <SidebarButton :isActive="idex=='1'">
        <template #title>Postings</template>
      </SidebarButton>
      <SidebarButton :isActive="idex=='2'">
        <template #title>Challenges</template>
      </SidebarButton>
      <SidebarButton :isActive="idex=='3'">
        <template #title>Rankings</template>
      </SidebarButton>
      <SidebarButton :isActive="idex=='4'">
        <template #title>Profile</template>
      </SidebarButton>
    </div>
    <div class="content">
      <slot>Can't find content</slot>
    </div>
  </div>
</template>

<style scoped>
#logo{
  width: 88px;
  height: 88px;
  background-color: orange;
}
.sidebar.bg {
  width: 88px;
  height: 100vh;
  left: 0;
  top: 0;
  background-color: #d9d9d9;
}
.content {
  width: 100%;
  height: 100vh;
  align-items: center;
  align-content: center;
}
.sidebar.button {
  width: 100%;
  height: 64px;
}
</style>