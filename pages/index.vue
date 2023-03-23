<template>
  <el-card class="box-card">
    <NuxtLink to="/home" class="link-base">
      <FieldButton type="success" plain :text="home" />
    </NuxtLink>
    <NuxtLink to="/about" class="link-base">
      <FieldButton :type="'success'" plain :text="about" />
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
const about = 'About';
const home = 'Home';
</script>
<style>
.link-base {
  text-decoration: auto;
}
</style>
