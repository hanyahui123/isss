<template>
  <div class="home">
    <!-- 首页 -->
    <el-container style="height: 700px; border: 1px solid #eee" class="aritle-page">
      <el-aside width="200px">
        <div class="logo">logo</div>
        <el-menu :default-openeds="['1', '3']" active-text-color="#0086fe">
          <el-submenu index="3">
            <template slot="title">
              <span>复旦软件园项目点</span>
            </template>

            <el-submenu index="1-4">
              <template slot="title">
                <i class="el-icon-location"></i>
                <span>项目信息维护</span>
              </template>
              <el-menu-item index="1-4-1">项目管理</el-menu-item>
              <el-menu-item index="1-4-2">数据手机审核</el-menu-item>
              <el-menu-item index="1-4-3">客户信息维护</el-menu-item>
            </el-submenu>
          </el-submenu>
        </el-menu>
      </el-aside>
      <!-- 导航标签 -->

      <el-container style="background:#eef5fd;height:1124px">
        <el-header style="text-align: right; font-size: 12px;">
          <el-dropdown>
            <i class="el-icon-setting" style="margin-right: 15px"></i>
          </el-dropdown>
          <span>权限设置</span>
        </el-header>
        <!-- heard 权限设置 -->

        <div class="content">
          <div class="content_1">
            <span>项目名称：</span>
            <el-input v-model="input" placeholder="请输入内容" class="ipt"></el-input>
            <span>项目负责人：</span>
            <el-input v-model="input" placeholder="请输入内容" class="ipt"></el-input>
            <div class="btn">
              <el-button class="btn_1">搜索</el-button>
              <el-button class="btn_2">重置</el-button>
            </div>
          </div>

          <el-button class="btn_3" type="text" @click="dialogFormVisible = true">新建</el-button>
          <!-- 弹出框 -->

          <el-dialog title="新建项目" :visible.sync="dialogFormVisible" width="1000px">
            <div class="con">项目详情</div>
            <div class="form">
              <p>客户名称:</p>
              <el-input placeholder="请输入内容" class="ipt_1"></el-input>
              <div class="from_1">
                <div class="from_1_1">
                  <p>项目名称:</p>
                  <el-input placeholder="请输入内容" class="ipt_1"></el-input>
                </div>
                <div class="from_1_1">
                  <p>项目名称:</p>
                  <el-input placeholder="请输入内容" class="ipt_1"></el-input>
                </div>
              </div>
            </div>
            <div class="form"></div>

            <!-- <el-form :label-position="labelPosition" label-width="80px" :model="formLabelAlign">
              <el-form-item label="名称">
                <el-input v-model="formLabelAlign.name"></el-input>
              </el-form-item>
              <el-form-item label="活动区域">
                <el-input v-model="formLabelAlign.region"></el-input>
              </el-form-item>
              <el-form-item label="活动形式">
                <el-input v-model="formLabelAlign.type"></el-input>
              </el-form-item>
            </el-form>
            <div slot="footer" class="dialog-footer">
              <el-button @click="dialogFormVisible = false">取 消</el-button>
              <el-button type="primary" @click="dialogFormVisible = false">确 定</el-button>
            </div>-->
          </el-dialog>

          <!-- <div>
            <el-main>
              <el-table :data="tableData">
                <el-table-column prop="date" label="日期" width="140"></el-table-column>
                <el-table-column prop="name" label="姓名" width="120"></el-table-column>
                <el-table-column prop="address" label="地址"></el-table-column>
              </el-table>
            </el-main>
          </div>-->
        </div>
      </el-container>
    </el-container>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    const item = {
      date: "2016-05-02",
      name: "王小虎",
      address: "上海市普陀区金沙江路 1518 弄"
    };
    return {
      input: "",
      tableData: Array(20).fill(item),
      dialogTableVisible: false,
      dialogFormVisible: false,
      form: {
        name: "",
        region: "",
        date1: "",
        date2: "",
        delivery: false,
        type: [],
        resource: "",
        desc: ""
      },
      labelPosition: "right",
      formLabelAlign: {
        name: "",
        region: "",
        type: ""
      },
      formLabelWidth: "120px"
    };
  },
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    }
  }
};
</script>

<style scoped>
.el-aside {
  background: #08395b;
  height: 1124px;
}
.logo {
  width: 66px;
  height: 57px;
  margin: 0 auto;
  background: #b3c0d1;
}
.el-submenu {
  background-color: #08395b;
  width: 200px;
  height: 90px;
}
.el-submenu span {
  color: #8cb4d8; /*  菜单颜色 */
}

.el-menu-item {
  /*子菜单 */
  background-color: #08395b;
  color: #8cb4d8;
  text-align: center;
}
.el-header {
  background: #fff;
  border: 1px solid #eee;
  width: 1290px;
  margin-left: 20px;
  margin-top: 10px;
  color: #0086fe;
  line-height: 60px;
}
.content {
  width: 1290px;
  height: 1008px;
  margin-left: 20px;
  margin-top: 10px;
  border: 1px solid #eee;
  background: #fff;
}
.content_1 {
  margin-top: 25px;
  width: 100%;
  height: 40px;
}
.content_1 span {
  display: block;
  font-size: 22px;
  color: #818a8f;
  float: left;
  height: 40px;
  margin-left: 31px;
  line-height: 40px;
}
.ipt {
  width: 230px;
  height: 40px;
  float: left;
  margin-left: 20px;
}
.btn {
  float: right;
}
.btn_1 {
  border: none;
  width: 120px;
  height: 40px;
  background: #08395b;
  color: #fff;
  float: left;
  margin-right: 18px;
}
.btn_2 {
  border: none;
  width: 120px;
  height: 40px;
  background: #08395b;
  color: #fff;
  margin-right: 18px;
  float: left;
}
.btn_3 {
  margin-left: 31px;
  margin-top: 42px;
  border: none;
  width: 120px;
  height: 40px;
  background: #08395b;
  color: #fff;
}

.con {
  width: 843px;
  margin-left: 80px;
  border-bottom: 1px solid #eee;
  margin-bottom: 20px;
  font-size: 26px;
  color: #818a8f;
  line-height: 40px;
}
.txt span {
  margin-left: 158px;
}
.form {
  width: 690px;
  height: 500px;
  background: #f00;
  margin-left: 158px;
}
.form p {
  font-size: 22px;
  margin-bottom: 4px;
}
.form_1 {
  width: 100%;
}
.from_1_1 {
  float: left;
  margin-right: 45px;
  margin-top: 34px;
}
</style>


<style>
/*  全局样式  要加独一无二类名 */
.home .el-dialog__header {
  height: 80px;
  background: #8cb4d8;
  border-radius: 12px 12px 0 0;
}
.home .el-dialog__title {
  color: #fff;
  line-height: 80px;
}
.home .el-dialog {
  border-radius: 12px;
}

.home .el-input {
  width: 300px;
  height: 40px;
}
</style>


