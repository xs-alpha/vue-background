<template>
  <el-header>
    <div class="l-content">
      <el-button size="small" @click="handleCollapse">
        <el-icon :size="20">
          <Menu />
        </el-icon>
      </el-button>
      <h3>首页</h3>
    </div>

    <div class="r-content">
      <el-dropdown>
    <span class="el-dropdown-link">
      <img class="user" :src="getImgSrc('avatar')" alt="头像">
    </span>
        <template #dropdown>
          <el-dropdown-menu>
            <el-dropdown-item>个人中心</el-dropdown-item>
            <el-dropdown-item>退出</el-dropdown-item>
          </el-dropdown-menu>
        </template>
      </el-dropdown>
    </div>
<!--    <div>大闺头</div>-->
  </el-header>
</template>

<script>
import {useStore} from "vuex";

export default {
  name: "CommonHeader",
  setup(){
    let store = useStore()
    const getImgSrc=(user)=>{
      return new URL(`../assets/images/${user}.png`, import.meta.url).href;
    };
    let handleCollapse =()=>{
      store.commit("updateIsCollapse")
    }
    return {
      getImgSrc,
      handleCollapse
    }
  }
}
</script>

<style lang="less" scoped>
header{
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  background-color: #333;
}
.r-content{
  .user{
    width: 40px;
    height: 40px;
    border-radius: 50%;
  }
}
.l-content{
  display: flex;
  align-items: center;
  .el-button{
    margin-right: 20px;
  }
  h3{
    color: #fff;
  }
}


</style>