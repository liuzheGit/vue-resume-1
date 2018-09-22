<template>
  <div>
    <h2>联系方式</h2>
    <hr>
    <el-form :label-position="'top'" label-width="80px">
      <el-form-item label="电话">
        <el-input v-model="contacts.phone"></el-input>
      </el-form-item>
      <el-form-item label="邮箱">
          <el-input v-model="contacts.email"></el-input>
      </el-form-item>
       <el-form-item label="微信">
        <el-input v-model="contacts.wecheat"></el-input>
      </el-form-item>
      <el-form-item label="QQ">
        <el-input v-model="contacts.qq"></el-input>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  props: ["contacts"],
  methods: {}
};
</script>

