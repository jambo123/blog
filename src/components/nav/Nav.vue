<template>
  <div class="nav">
    <div class="nav-content">
      <el-row :gutter="20">
        <el-col :span="3">
          <img class="logo" src="@/assets/logo.png" />
        </el-col>
        <el-col :span="16">
          <el-menu :default-active="activeIndex" mode="horizontal" @select="handleSelect">
            <el-menu-item :key="item.index" v-for="item in list" :index="item.index" :route="item.path">
              {{ item.name }}
            </el-menu-item>
          </el-menu>
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Nav',
  data () {
    return {
      activeIndex: '1',
      list: [{
        index: '1',
        path: '/',
        name: '首页'
      },
      {
        index: '2',
        path: '/article',
        name: '文章'
      },
      {
        index: '3',
        path: '/project',
        name: '项目'
      },
      {
        index: '4',
        path: '/message',
        name: '留言'
      },
      {
        index: '5',
        path: '/about',
        name: '关于我'
      }]
    }
  },
  methods: {
    handleSelect (index, keyPath) {
      console.log(index)
    }
  }
}
</script>

<style>
.nav {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1000;
  width: 100%;
  border-bottom: 1px solid #eee;
  background-color: #fff;
}
.logo {
  height: 40px;
  margin: 0;
  margin-top: 10px;
}
.nav-content {
  width: 1200px;
  margin: 0 auto;
}
</style>
