<template>
   <el-container>
    <el-header>
      <el-row>
        <el-col :span="4">
          <img src="@/assets/logo.png" alt="">
        </el-col>
        <el-col :span="18" class="middle">
          电商后台管理系统
        </el-col>
        <el-col :span="2">
          <a href="#" class="logout">退出</a>
        </el-col>
        </el-row>
    </el-header>
    <el-container>
        <el-aside width="200px">
          <el-menu
          :unique-opened="true"
          :router="true"
          default-active="0"
          class="el-menu-vertical-demo">
            <el-submenu index="1">
                <template slot="title">
                <i class="el-icon-location"></i>
                <span>用户管理</span>
                </template>
                <el-menu-item-group>
                <el-menu-item index="1-1"><i class="el-icon-view"></i>用户列表</el-menu-item>
                </el-menu-item-group>
            </el-submenu>
            <el-submenu index="2">
                <template slot="title">
                <i class="el-icon-location"></i>
                <span>权限管理</span>
                </template>
                <el-menu-item-group>
                <el-menu-item index="1-1"><i class="el-icon-view"></i>用户列表</el-menu-item>
                <el-menu-item index="1-2"><i class="el-icon-view"></i>权限列表</el-menu-item>
                </el-menu-item-group>
            </el-submenu>
            <el-submenu index="3">
                <template slot="title">
                <i class="el-icon-location"></i>
                <span>用户管理</span>
                </template>
                <el-menu-item-group>
                <el-menu-item index="1-1"><i class="el-icon-view"></i>商品列表</el-menu-item>
                <el-menu-item index="1-2"><i class="el-icon-view"></i>分类参数</el-menu-item>
                <el-menu-item index="1-2"><i class="el-icon-view"></i>商品分类</el-menu-item>
                </el-menu-item-group>
            </el-submenu>
          </el-menu>
          </el-aside>
          <el-main>Main</el-main>
    </el-container>
  </el-container>
</template>

<script>
export default {
  beforeCreate() {
    const token = sessionStorage.getItem('token')
    if (!token) {
      this.$message.warning('请先登录')
      this.$router.push('/login')
    }
  }
}
</script>

<style>
.el-container{
height: 100%;
}
.middle{
font-size: 28px;
color: #fff;
text-align: center
}
.logout{
display: block;
text-decoration: none;
color: #333;
text-align: right
}
.el-header, .el-footer {
background-color: #B3C0D1;
color: #333;
/* text-align: center; */
line-height: 60px;
padding: 0
}

.el-aside {
background-color: #D3DCE6;
color: #333;
/* text-align: center; */
background-color: #fff;
line-height: 200px;
}

.el-main {
background-color: #E9EEF3;
color: #333;
text-align: center;
line-height: 160px;
}

</style>
