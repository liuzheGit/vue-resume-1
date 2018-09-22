<template>
  <div>
    <h2 @click="tlm">{{title}}</h2>
    <hr>
    <el-form label-position="top" label-width="80px">   
      <div class="container"
            v-for="(item, index) in items"
            :key="index">
        <el-button class="remove-button" size="small" type="danger" v-on:click="removeItem(index)">删除</el-button>
        <el-form-item v-for="(key, index) in keys" :key="index" :label="labels[key] || key">
          <el-input v-model="item[key]"></el-input>
        </el-form-item>
      </div>
      
    </el-form>
    <el-button type="primary" v-on:click="addItem">添加</el-button>
  </div>
</template>

<script>
export default {
  props: ['items', 'labels', 'title'],
  data(){
    return {
      emptyObj: {}
    }
  },
  created(){
    Object.keys(this.items[0]).map((key)=>{
        this.emptyObj[key] = '';
    })
  },
  computed:{
    keys(){
      return Object.keys(this.items[0])
    }
  },
  methods:{  
    addItem(){
      // const empty = {};
      // this.keys.map((key)=>{
      //   empty[key] = '';
      // })
      this.items.push(this.emptyObj)
    },
    removeItem(index){
       this.items.splice(index, 1);
    },
    tlm(){
      console.log(this.emptyObj)
    }
  }
}
</script>

