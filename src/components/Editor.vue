<template>
  <div id="editor">
    <div class="menu">
      <ol>
        <li v-for="(i, index) in icons" v-bind:key="index"
            v-bind:class="{active: currentTab === index}"
            v-on:click="currentTab = index" >
          <svg class="icon" aria-hidden="true">
            <use v-bind:xlink:href="'#icon-'+ i +''"></use>1
          </svg>
        </li>
      </ol>
    </div>
    <div class="editor-content">
      <ol>
        <li v-bind:class="{active: currentTab===0}">
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
        </li>
        <li v-bind:class="{active: currentTab===1}">
          <h2>工作经历</h2>
          <hr>
          <el-form :label-position="'top'" 
                   label-width="80px"
                  v-for="(work, index) in worksExprience"
                  v-bind:key="index">
            <el-button class="remove-button" size="small" type="danger" v-on:click="removeWork(index)">删除</el-button>
            <el-form-item label="公司名称">
              <el-input v-model="work.name"></el-input>
            </el-form-item>
            <el-form-item label="工作内容">
              <el-input v-model="work.content"></el-input>
            </el-form-item>
          </el-form>
          <el-button type="primary" v-on:click="addWorks">添加</el-button>
        </li>
      </ol>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      currentTab: 0,
      icons: ['shenfenzhenghao', 'workfillmtui', 'book', 'code', 'icon22', 'phone'],
      personalInfo:{
        name: '',
        city: '',
        birth: ''
      },
      worksExprience: [
        {name: '', content: ''},
      ]
    }
  },
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

<style lang="scss">
  #editor {
    min-height: 100px;
    display: flex;
    > div {
    }
    .menu{
      li {
        padding: 16px;
        font-size: 24px;
        background-color: black;
        > svg{
          fill: white;
        }
      }
      li.active{
        background-color: white;
        > svg{
          fill: black;
        }
      }
    }
    .editor-content{
      flex: 1;
      padding: 32px;
      overflow: auto;
      li {
        display: none;
        &.active{
          display: block;
        }
        form{
          position: relative;
        }
        .remove-button{
          position: absolute;
          right: 50px;
        }
      }
    }
  }
</style>

