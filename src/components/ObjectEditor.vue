<template>
  <div>
    <h2>{{title}}</h2>
    <hr>
    <el-form :label-position="'top'" label-width="80px">
      <el-form-item label="姓名">
        <el-input v-model="object.name"></el-input>
      </el-form-item>
      <el-form-item label="城市">
        <el-input v-model="object.city"></el-input>
      </el-form-item>
      <el-form-item label="出生年月">
        <el-input v-model="object.birth"></el-input>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  props: ['object', 'title'],
  methods:{
  
  }
}
</script>

