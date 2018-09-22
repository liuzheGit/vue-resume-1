<template>
  <div>
    <h2>学习经历</h2>
    <hr>
    <el-form label-position="top" label-width="80px">   
      <div class="container"
            v-for="(item, index) in items"
            v-bind:key="index">
        <el-button class="remove-button" size="small" type="danger" v-on:click="removeItem(index)">删除</el-button>
        <el-form-item label="学校">
          <el-input v-model="item.name"></el-input>
        </el-form-item>
        <el-form-item label="持续时间">
          <el-input v-model="item.durtion"></el-input>
        </el-form-item>
        <el-form-item label="学位">
          <el-input v-model="item.degree"></el-input>
        </el-form-item>
      </div>
      
    </el-form>
    <el-button type="primary" v-on:click="addItem">添加</el-button>
  </div>
</template>

<script>
export default {
  props: ['items'],
  methods:{
    addItem(){
      this.items.push({name: '', durtion: '', degree: ''})
    },
    removeItem(index){
       this.items.splice(index, 1);
     }
  }
}
</script>

