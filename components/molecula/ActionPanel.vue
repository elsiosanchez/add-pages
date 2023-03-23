<template>
  <div>
    <el-card>
      <p :style="{ 'text-align': textAling }">
        <span :style="{ float: slotsAlingLeft }">
          <slot name="slotsLeft" />
        </span>
        <el-button type="info" @click="actionClear">
          <template #icon>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              height="48"
              viewBox="0 96 960 960"
              width="48"
            >
              <path
                d="m650 641-42-42 134-105-262-204-102 79-43-43 145-112 360 280-190 147Zm86 86-43-43 97-75 50 37-104 81Zm94 264L641 801 480 926 120 646l50-37 310 241 118-92-43-43-75 59-360-280 120-94L73 234l43-43 757 757-43 43ZM493 484Z"
              />
            </svg>
          </template>
        </el-button>
        <el-button type="danger" @click="actionClose">
          <template #icon>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              height="48"
              viewBox="0 96 960 960"
              width="48"
            >
              <path
                d="m249 849-42-42 231-231-231-231 42-42 231 231 231-231 42 42-231 231 231 231-42 42-231-231-231 231Z"
              />
            </svg>
          </template>
        </el-button>
        <el-button type="primary" @click="actionCheck">
          <template #icon>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              height="48"
              viewBox="0 96 960 960"
              width="48"
            >
              <path d="M378 810 154 586l43-43 181 181 384-384 43 43-427 427Z" />
            </svg>
          </template>
        </el-button>
        <span :style="{ float: slotsAlingRight }">
          <slot name="slotsRight" />
        </span>
      </p>
    </el-card>
  </div>
</template>
<script lang="ts" setup>
const props = defineProps({
  showClear: {
    type: Boolean,
    required: true,
  },
  showClose: {
    type: Boolean,
    required: true,
  },
  showCheck: {
    type: Boolean,
    required: true,
  },
  actionClear: {
    type: Function,
    default: (clean) => {
      console.info('Implement the Clean Method', clean);
    },
  },
  actionClose: {
    type: Function,
    default: (close) => {
      console.info('Implement the Close Method', close);
    },
  },
  actionCheck: {
    type: Function,
    default: (check) => {
      console.info('Implement the Check Method', check);
    },
  },
  disabledClear: {
    type: Boolean,
    default: false,
  },
  disabledClose: {
    type: Boolean,
    default: false,
  },
  disabledCheck: {
    type: Boolean,
    default: false,
  },
  textAling: {
    type: String,
    required: false,
    default: 'Right',
  },
  slotsLeft: String,
  slotsRight: String,
  slotsAlingLeft: String,
  slotsAlingRight: String,
});
</script>

<style scoped>
.demo-fit {
  display: flex;
  text-align: center;
  justify-content: space-between;
}
.demo-fit .block {
  flex: 1;
  display: flex;
  flex-direction: column;
  flex-grow: 0;
}

.demo-fit .title {
  margin-bottom: 10px;
  font-size: 14px;
  color: var(--el-text-color-secondary);
}
</style>
