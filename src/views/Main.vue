<template>
  <div class="common-layout">
    <el-container class="lay-container">
      <!--        <el-aside width="200px">Aside</el-aside>-->
      <common-aside></common-aside>
      <el-container class="r-content">
        <!--      <el-header>Header</el-header>-->
        <common-header></common-header>
        <el-main>
          <router-view></router-view>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
import {defineComponent} from "vue";
import CommonHeader from "../components/CommonHeader.vue";
import CommonAside from "../components/CommonAside.vue";

export default {
  name: "Main",
  components: {CommonAside, CommonHeader}
}
</script>

<style lang="less" scoped>
.el-container{
  flex-wrap: wrap;
  align-items: flex-start;
}

.common-layout{
  height: 100%;
  & > .el-container{
    height: 100%;
    & > .el-aside{
      height: 100%;
      background-color: #545c64;
    }
  }
}
</style>