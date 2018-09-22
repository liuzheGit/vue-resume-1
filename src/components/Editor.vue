<template>
  <div id="editor">
    <div class="menu">
      <ol>
        <li v-for="(i, index) in icons" v-bind:key="index"
            v-bind:class="{active: currentTab === index}"
            v-on:click="currentTab = index" >
          <svg class="icon" aria-hidden="true">
            <use v-bind:xlink:href="`#icon-${i}`"></use>1
          </svg>
        </li>
      </ol>
    </div>
    <div class="editor-content">
      <ol>
        <li v-bind:class="{ active: currentTab === 0}">
          <ObjectEditor v-bind:title="'个人信息'" v-bind:object="personalInfo" v-bind:labels="{name: '姓名', city: '城市', birth: '出生年月'}"/>
        </li>
        <li v-bind:class="{ active: currentTab === 1}">
          <ArrayEditor v-bind:title="'工作经历'" v-bind:items="workItems" v-bind:labels="{name: '公司名称', content: '工作内容'}"/>
        </li>
        <li v-bind:class="{ active: currentTab === 2}">
          <ArrayEditor v-bind:title="'学习经历'" v-bind:items="schoolItems" v-bind:labels="{name: '学校', durtion: '时间', degree: '学位'}"/>
        </li>
      </ol>
    </div>
  </div>
</template>

<script>
import ObjectEditor from './ObjectEditor'
import ArrayEditor from './ArrayEditor'
export default {
  components:{
    ObjectEditor, ArrayEditor
  },
  data(){
    return {
      currentTab: 0,
      icons: ['shenfenzhenghao', 'workfillmtui', 'book', 'code', 'icon22', 'phone'],
      personalInfo:{
        name: '',
        city: '',
        birth: ''
      },
      workItems: [
        {name: '', content: ''},
      ],
      schoolItems:[
        {name: '', durtion: '', degree: ''},
      ]
    }
  },
  methods:{

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
        .container{
          position: relative;
        }
        .remove-button{
          position: absolute;
          right: 4px;
        }
      }
    }
  }
</style>

