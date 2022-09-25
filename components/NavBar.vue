<template>
    <el-menu
      :default-active="activeIndex"
      class="el-menu-demo"
      mode="horizontal"
      :ellipsis="false"
      @select="handleSelect"
    >
      <el-menu-item @click="navigate('/')" index="/">Frume</el-menu-item>
      <div class="flex-grow" />
      <el-menu-item @click="navigate('/privacy')" index="/privacy">Privacy Policy</el-menu-item>
      <!-- <el-sub-menu index="2">
        <template #title>Workspace</template>
        <el-menu-item index="2-1">item one</el-menu-item>
        <el-menu-item index="2-2">item two</el-menu-item>
        <el-menu-item index="2-3">item three</el-menu-item>
        <el-sub-menu index="2-4">
          <template #title>item four</template>
          <el-menu-item index="2-4-1">item one</el-menu-item>
          <el-menu-item index="2-4-2">item two</el-menu-item>
          <el-menu-item index="2-4-3">item three</el-menu-item>
        </el-sub-menu>
      </el-sub-menu> -->
    </el-menu>
  </template>
  
  <script lang="ts" setup>
  import { ref } from 'vue'
  import {
  ElMenu,
  ElMenuItem,
} from "element-plus";  
const router = useRouter();

function navigate(path: string){
  return navigateTo({
    path: path,
    // query: {
    //   name: name.value,
    //   type: type.value
    // }
  })
}
    console.log(router)
  const activeIndex = ref('/')
  activeIndex.value = router.currentRoute.value.path
  
  const handleSelect = (key: string, keyPath: string[]) => {
    console.log(key, keyPath)
  }
  </script>
  
  <style>
  .flex-grow {
    flex-grow: 1;
  }
  .el-menu {
    max-width: 980px;
    margin: 0 auto;
  }
  </style>