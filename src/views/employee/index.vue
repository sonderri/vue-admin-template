<template>
  <div class="emplyee-container">
    员工管理
    <!-- <div class="dashboard-text">name: {{ name }}</div> -->
    <div class="tableBar" style="height: 70px;">
      <el-input style="width: 200px;" placeholder="请输入员工姓名" v-model="input">
        <i slot="prefix" class="el-input__icon el-icon-search" />
      </el-input>
      <el-button type="warning">+添加员工</el-button>
    </div>
    <div class="tableMain">
      <el-table :data="tableData" stripe style="width: 100%">
        <el-table-column prop="name" label="员工姓名" width="180" />
        <el-table-column prop="id" label="账号" width="180" />
        <el-table-column prop="phone" label="手机号" />
        <el-table-column prop="idState" label="账号状态" />
        <el-table-column prop="operate" label="操作" />
      </el-table>
    </div>
    <div class="tableEnd"></div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  name: 'Dashboard',
  data() {
    return {
      input: '',
      tableData: [{
        name: '小鹏',
        id: '32321231',
        phone: '181123121',
        idState: '正常',
        operater: '操作'
      }, {
        date: '2016-05-04',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1517 弄'
      }, {
        date: '2016-05-01',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1519 弄'
      }, {
        date: '2016-05-03',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1516 弄'
      }]
    }
  },
  computed: {
    ...mapGetters([
      'name'
    ])
  }
}
</script>

<style lang="scss" scoped>
.dashboard {
  &-container {
    margin: 30px;
  }

  &-text {
    font-size: 30px;
    line-height: 46px;
  }

  .tableBar {

    .input {
      width: 200px;
    }

  }

}
</style>
