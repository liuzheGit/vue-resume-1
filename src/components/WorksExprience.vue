<template>
  <div>
    <h2>工作经历</h2>
    <hr>
    <el-form label-position="top" label-width="80px">   
      <div class="container"
            v-for="(work, index) in worksExprience"
            v-bind:key="index">
        <el-button class="remove-button" size="small" type="danger" v-on:click="removeWork(index)">删除</el-button>
        <el-form-item label="公司名称">
          <el-input v-model="work.name"></el-input>
        </el-form-item>
        <el-form-item label="工作内容">
          <el-input v-model="work.content"></el-input>
        </el-form-item> 
      </div>
      
    </el-form>
    <el-button type="primary" v-on:click="addWorks">添加</el-button>
  </div>
</template>

<script>
export default {
  props: ['worksExprience'],
  methods:{
    addWorks(){
      this.worksExprience.push({name: '', content: ''})
    },
    removeWork(index){
       this.worksExprience.splice(index, 1);
     }
  }
}
</script>

