<template>
  <el-card class="box-card">
    <NuxtLink to="/test">
      <el-button type="primary" plain> Test Page </el-button>
    </NuxtLink>
    <NuxtLink to="/about" class="n-link-base">
      <el-button type="success" plain> About </el-button>
    </NuxtLink>
    <el-card shadow="never">
      <p style="text-align: center">
        Current route: <code>{{ route.path }}</code>
      </p>
    </el-card>
  </el-card>
</template>
<script setup lang="ts">
const route = useRoute();
</script>
