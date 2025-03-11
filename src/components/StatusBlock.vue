<template>
  <div class="status-block" :style="{ backgroundColor: blockColor }"></div>
</template>

<script>
export default {
  props: {
    status: {
      type: Number,
      required: true,
      validator: value => value === 0 || value === 1 // 限制状态值为0或1
    }
  },
  computed: {
    blockColor() {
      return this.status === 1 ? 'blue' : 'gray'; // 状态1为蓝色，0为灰色
    }
  }
};
</script>

<style scoped>
.status-block {
  width: 100%;
  height: 60%;
  margin: 6% 0 10% 0;
    border-radius: 3px;
  /* display: inline-block; */
}
</style>