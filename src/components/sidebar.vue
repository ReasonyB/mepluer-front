<script setup>
import { ref } from 'vue';
import SidebarButton from './SidebarButton.vue';
const idex = ref(1);
const isLogIn = ref(true);

</script>

<template>
  <div class="sidebar-container" style="display: flex;">
    <div class="sidebar bg" style="display: flex; flex-direction: column; justify-content: space-between;">
      <div class="sidebar align">
        <div id="logo"></div>
        <SidebarButton :isActive="idex=='0'">
          <template #icon><img class="icon" src="../assets/tasks.svg"></template>
          <template #title>Tasks</template>
        </SidebarButton>
        <SidebarButton :isActive="idex=='1'">
          <template #icon><img class="icon" src="../assets/posting.svg"></template>
          <template #title>Postings</template>
        </SidebarButton>
        <SidebarButton :isActive="idex=='2'">
          <template #icon><img class="icon" src="../assets/challenge.svg"></template>
          <template #title>Challenges</template>
        </SidebarButton>
        <SidebarButton :isActive="idex=='3'">
          <template #icon><img class="icon" src="../assets/ranking.svg"></template>
          <template #title>Rankings</template>
        </SidebarButton>
        <SidebarButton :isActive="idex=='4'">
          <template #icon><img class="icon" src="../assets/profile.svg"></template>
          <template #title>Profile</template>
        </SidebarButton>
      </div>
      <div class="sidebar align">
        <div v-if="isLogIn">
          <div class="sidebar auth"><img src="../assets/selfi.png" width="48px" height="48px"></div>
          <div class="sidebar auth icon"><img src="../assets/hams.svg" width="32px" height="32px"></div>
        </div>
        <div v-else>
          <button class="sidebar auth">personal</button>
          <p style="height: auto; margin: 0px; margin-bottom: 10px; margin-top:10px; background-color: blue;">LogIn</p>
        </div>
      </div>
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
.sidebar.align{
  display: flex;
  flex-direction: column;
  align-items: center;
}
.content {
  width: 100%;
  height: 100vh;
  align-items: center;
  align-content: center;
}
.sidebar.auth {
  display: flex;
  width: 50px;
  height: 50px;
  align-items: center;
  justify-content: center;
  background-color: #5B5B5B;
  margin-top:8px;
  margin-bottom: 8px;
}
.sidebar.auth:hover {
  background-color: #FEA190;
}

</style>