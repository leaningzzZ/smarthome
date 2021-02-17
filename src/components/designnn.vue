<template>
  <div class="container">
    <div class="header">
      <el-steps :active="active" finish-status="success" size="20">
        <el-step title="步骤 1 用户登录"></el-step>
        <el-step title="步骤 2 设计智能系统"></el-step>
        <el-step title="步骤 3 评价智能系统"></el-step>
      </el-steps>
    </div>
    <div class="body">
      <div class="content">
          <div class="leftButton" @click="setShowLeftModal()">
              下拉
          </div>
          <div class="leftModal" v-show="showLeftModal">
          safs
      </div>
      </div>
    </div>
    <div class="footer">
      <el-container>
        <el-menu
          :default-active="activeIndex"
          class="el-menu-demo"
          mode="horizontal"
          @select="handleSelect"
        >
          <el-menu-item index="1"
            ><a href="https://www.baidu.com" target="_blank"
              >总览</a
            ></el-menu-item
          >
          <el-menu-item index="2"
            ><a href="https://www.ele.me" target="_blank">客厅</a></el-menu-item
          >
          <el-menu-item index="3"
            ><a href="https://www.ele.me" target="_blank">主卫</a></el-menu-item
          >
          <el-menu-item index="4"
            ><a href="https://www.ele.me" target="_blank"
              >卫生间</a
            ></el-menu-item
          >
          <el-menu-item index="5"
            ><a href="https://www.ele.me" target="_blank">厨房</a></el-menu-item
          >
        </el-menu>
        <el-button type="text" @click="repository = true"
          >打开产品库 Drawer</el-button
        >
        <el-button type="text" @click="list = true"
          >打开产品清单 Drawer</el-button
        >
        <el-button style="margin-top: 12px" @click="next">上一步</el-button>
        <el-button style="margin-top: 12px" @click="next">下一步</el-button>
      </el-container>
    </div>
  </div>
</template>
<script>
export default {
  name: "design",
  props: {},
  data(){
    return{
      active: 0,
      activeIndex: '1',
      repository: true,
      list: true,
      gridData: [{
        date: '2016-05-02',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      }, {
        date: '2016-05-04',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      }, {
        date: '2016-05-01',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      }, {
        date: '2016-05-03',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      }],
      showLeftModal:false
    }
  },
  methods:{
    next() {
      if (this.active++ > 2) this.active = 0;
    },
    handleSelect(key, keyPath) {
      console.log(key, keyPath);
    },
    setShowLeftModal(){
        console.log(1)
        this.showLeftModal = !this.showLeftModal
    }
  }
}
</script>
<style scoped>
.content {
  position: relative;
  height: 800px;
  background: url("../assets/all.png") no-repeat;
  background-size: cover;
}
.leftButton{
    position:absolute;
    left: 20px;
    top: 50%;
    transform: translateY(-50%)
}
.leftModal{
    width: 300px;
    height: 500px;
    background: white;
    position: relative;
    left: 50px;
    top: 50%;
    transform: translateY(-50%)
}
</style>