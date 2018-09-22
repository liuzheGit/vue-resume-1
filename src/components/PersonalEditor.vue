<template>
  <div>
    <h2>个人信息</h2>
    <hr>
    <el-form :label-position="'top'" label-width="80px">
      <el-form-item label="姓名">
        <el-input v-model="personalInfo.name"></el-input>
      </el-form-item>
      <el-form-item label="城市">
        <el-input v-model="personalInfo.city"></el-input>
      </el-form-item>
      <el-form-item label="出生年月">
        <el-input v-model="personalInfo.birth"></el-input>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  props: ['personalInfo'],
  methods:{
  
  }
}
</script>

