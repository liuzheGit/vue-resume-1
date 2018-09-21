<template>
  <div id="topBar">
    <div class="log">
      MyResumer
    </div>
    <div class="action">
      <el-button type="primary">登录</el-button>
      <el-button type="success">注册</el-button>  
    </div>
  </div>
</template>

<style lang="scss">
  #topBar {
    display: flex;
    justify-content: space-between;
    position: relative;
    z-index: 1;
    box-shadow: 0 0 3px hsla(0, 0, 0, .5);
    > div {
      margin: 16px;
    }
  }
</style>

