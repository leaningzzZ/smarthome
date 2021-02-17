<template>
  <el-container>
    <el-header>
      <div style="border: 1px red solid">
        <el-steps :active="active" finish-status="success" size="20">
          <el-step title="步骤 1 用户登录"></el-step>
          <el-step title="步骤 2 设计智能系统"></el-step>
          <el-step title="步骤 3 评价智能系统"></el-step>
        </el-steps>
      </div>
    </el-header>

    <el-main>
      <div style="border: 1px olivedrab solid; position: relative">
        <img src="../assets/all.png" width="1205" height="570" style="position: absolute">
        <div>
          <h2>hahaha</h2>
        </div>

      </div>

      <div>
        <el-drawer
            title="产品库"
            :visible.sync="repository"
            direction="ltr"
            size="25%"
            :modal="true"
            :modal-append-to-body="false"
            :wrapper-closable="false"
            :append-to-body="true"
        >
          <el-table :data="gridData">
            <el-table-column property="date" label="日期" width="150"></el-table-column>
            <el-table-column property="name" label="姓名" width="200"></el-table-column>
            <el-table-column property="address" label="地址"></el-table-column>
          </el-table>
        </el-drawer>

        <el-drawer
            title="产品清单"
            :visible.sync="list"
            direction="rtl"
            size="25%"
            :modal="false"
            :wrapper-closable="false"
            :append-to-body="true"

        >
          <el-table :data="gridData">
            <el-table-column property="date" label="日期" width="150"></el-table-column>
            <el-table-column property="name" label="姓名" width="200"></el-table-column>
            <el-table-column property="address" label="地址"></el-table-column>
          </el-table>
        </el-drawer>
      </div>

    </el-main>

    <el-footer>
      <el-container>
        <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
          <el-menu-item index="1"><a href="https://www.baidu.com" target="_blank">总览</a></el-menu-item>
          <el-menu-item index="2"><a href="https://www.ele.me" target="_blank">客厅</a></el-menu-item>
          <el-menu-item index="3"><a href="https://www.ele.me" target="_blank">主卫</a></el-menu-item>
          <el-menu-item index="4"><a href="https://www.ele.me" target="_blank">卫生间</a></el-menu-item>
          <el-menu-item index="5"><a href="https://www.ele.me" target="_blank">厨房</a></el-menu-item>
        </el-menu>
        <el-button type="text" @click="repository = true">打开产品库 Drawer</el-button>
        <el-button type="text" @click="list = true">打开产品清单 Drawer</el-button>
        <el-button style="margin-top: 12px;" @click="next">上一步</el-button>
        <el-button style="margin-top: 12px;" @click="next">下一步</el-button>
      </el-container>
    </el-footer>
  </el-container>
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
    }
  },
  methods:{
    next() {
      if (this.active++ > 2) this.active = 0;
    },
    handleSelect(key, keyPath) {
      console.log(key, keyPath);
    },
  }
}
</script>

<style scoped>

</style>