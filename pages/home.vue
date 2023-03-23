<template>
  <el-card class="box-card">
    <NuxtLink to="/" class="link-base">
      <FieldButton :type="'success'" plain :text="back" />
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
const back = 'Go back';
</script>
