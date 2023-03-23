<template>
  <el-card>
    <div class="example-pagination-block">
      <el-pagination
        :default-current-page="currentPagePaginations"
        :page-size="pagerSize"
        :background="background"
        :hide-on-single-page="hide"
        :layout="layout"
        :total="totalPage"
        :disabled="disabled"
      />
    </div>
  </el-card>
</template>
<script lang="ts" setup>
import { computed } from 'vue';
const props = defineProps({
  background: {
    type: Boolean,
    default: true,
  },
  hide: {
    type: Boolean,
    default: false,
  },
  totalPage: {
    type: Number,
    default: 100,
  },
  disabled: {
    type: Boolean,
    default: false,
  },
  currentPage: {
    type: Number,
    default: 3,
  },
  pagerSize: {
    type: Number,
    default: 10,
  },
  layout: {
    type: String,
    default: 'total, prev, pager, next',
  },
});
const currentPagePaginations = computed(() => {
  return props.currentPage;
});
</script>

<style scoped>
.example-pagination-block + .example-pagination-block {
  margin-top: 10px;
}
.example-pagination-block .example-demonstration {
  margin-bottom: 16px;
}
</style>
