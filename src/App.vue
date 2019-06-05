<template>
  <div id="app">
    <ul>
      <items :model="item" v-for="(item, index) in list" :key="index"></items>
    </ul>
  </div>
</template>

<script>
import Items from "./components/Items.vue";

export default {
  name: "app",
  data() {
    return {
      list: [
        {
          menuName: "项目管理",
          childTree: [
            {
              menuName: "项目进度",
              childTree: [
                {
                  menuName: "项目一",
                  childTree: [{ menuName: "详细信息" }]
                }
              ]
            },
            {
              menuName: "任务安排"
            }
          ]
        },
        {
          menuName: "数据统计"
        },
        {
          menuName: "人员管理"
        }
      ]
    };
  },
  components: {
    Items
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
