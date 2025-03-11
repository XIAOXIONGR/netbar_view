<template>
  <div class="container">
    <div class="computer"
      v-for="(block, index) in statuses"
      :key="index"
      :style="getBlockStyle(block)"
    >
      <StatusBlock :status="block.status" />
    </div>
  </div>
  <div class="buttons">
    <button @click="updateStatuses">模拟状态更新</button>
  </div>
</template>

<script>
import StatusBlock from "@/components/StatusBlock.vue";

export default {
  components: {
    StatusBlock,
  },
  data() {
    return {
      statuses: [
        { status: 1, row: 1, col: 1, spanRow: 1, spanCol: 1 },
        { status: 1, row: 1, col: 2, spanRow: 1, spanCol: 1 },
       
        { status: 1, row: 1, col: 4, spanRow: 1, spanCol: 1 },
        { status: 1, row: 1, col: 5, spanRow: 1, spanCol: 1 },
     
        { status: 1, row: 1, col: 7, spanRow: 1, spanCol: 1 },
        { status: 1, row: 1, col: 8, spanRow: 1, spanCol: 1 },
        
        
     
        { status: 1, row: 1, col: 10, spanRow: 1, spanCol: 1 },
        { status: 1, row: 1, col: 11, spanRow: 1, spanCol: 1 },
        { status: 1, row: 1, col: 13, spanRow: 1, spanCol: 1 },
        { status: 1, row: 1, col: 14, spanRow: 1, spanCol: 1 },
        { status: 1, row: 1, col: 15, spanRow: 1, spanCol: 1 },
       

        { status: 1, row: 2, col: 1, spanRow: 1, spanCol: 1 },
        { status: 1, row: 2, col: 2, spanRow: 1, spanCol: 1 },
     
        { status: 1, row: 2, col: 4, spanRow: 1, spanCol: 1 },
        { status: 1, row: 2, col: 5, spanRow: 1, spanCol: 1 },
       
        { status: 1, row: 2, col: 7, spanRow: 1, spanCol: 1 },
        { status: 1, row: 2, col: 8, spanRow: 1, spanCol: 1 },
        { status: 1, row: 2, col: 10, spanRow: 1, spanCol: 1 },
        { status: 1, row: 2, col: 11, spanRow: 1, spanCol: 1 },
        { status: 1, row: 2, col: 1, spanRow: 1, spanCol: 1 },
        
        { status: 1, row: 2, col: 10, spanRow: 1, spanCol: 1 },
        { status: 1, row: 3, col: 1, spanRow: 1, spanCol: 1 },
        { status: 1, row: 3, col: 2, spanRow: 1, spanCol: 1 },
        { status: 1, row: 3, col: 4, spanRow: 1, spanCol: 1 },
        { status: 1, row: 3, col: 5, spanRow: 1, spanCol: 1 },
        { status: 1, row: 3, col: 7, spanRow: 1, spanCol: 1 },
        { status: 1, row: 3, col: 8, spanRow: 1, spanCol: 1 },
        { status: 1, row: 3, col: 10, spanRow: 1, spanCol: 1 },


        { status: 1, row: 3, col: 11, spanRow: 1, spanCol: 1 },
        
        { status: 1, row: 3, col: 14, spanRow: 1, spanCol: 1 },
        
        { status: 1, row: 4, col: 1, spanRow: 1, spanCol: 1 },
        { status: 1, row: 4, col: 2, spanRow: 1, spanCol: 1 },
        { status: 1, row: 4, col: 4, spanRow: 1, spanCol: 1 },
        { status: 1, row: 4, col: 5, spanRow: 1, spanCol: 1 },
        { status: 1, row: 4, col: 7, spanRow: 1, spanCol: 1 },


        { status: 1, row: 4, col: 8, spanRow: 1, spanCol: 1 },
        { status: 1, row: 4, col: 10, spanRow: 1, spanCol: 1 },


        { status: 1, row: 4, col: 11, spanRow: 1, spanCol: 1 },
        { status: 1, row: 4, col: 14, spanRow: 1, spanCol: 1 },
       
        { status: 1, row: 5, col: 14, spanRow: 1, spanCol: 1 },

        { status: 1, row: 6, col: 5, spanRow: 1, spanCol: 1 },
        { status: 1, row: 6, col: 6, spanRow: 1, spanCol: 1 },
        { status: 1, row: 6, col: 7, spanRow: 1, spanCol: 1 },
        { status: 1, row: 6, col: 8, spanRow: 1, spanCol: 1 },
        { status: 1, row: 6, col: 9, spanRow: 1, spanCol: 1 },
        
        // 添加更多方块
      ],
    };
  },
  methods: {
    updateStatuses() {
      this.statuses = this.statuses.map((block) => ({
        ...block, // 保留原有属性
        status: Math.floor(Math.random() * 2), // 更新 status 为随机值0或1
      }));
    },
    getBlockStyle(block) {
      return {
        gridRow: `${block.row} / span ${block.spanRow}`,
        gridColumn: `${block.col} / span ${block.spanCol}`,
      };
    },
  },
};
</script>

<style scoped>
.container {

  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: repeat(5, 1fr);
  gap: 10px;
  height: 100vh;
}
.computer{
    background-image: url(../assets/computer.png);
    background-size: 99% 99%; /* 宽高都缩小到50% */
  background-repeat: no-repeat;
}
.buttons {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
}
</style>
