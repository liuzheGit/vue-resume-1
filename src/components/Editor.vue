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
        <li v-bind:class="{ active: currentTab === 0}">
          <PersonalInfo v-bind:personalInfo="personalInfo" />
        </li>
        <li v-bind:class="{ active: currentTab === 1}">
          <WorksExprience v-bind:worksExprience="worksExprience" />
        </li>
        <li v-bind:class="{ active: currentTab === 2}">
          <SchoolEditor v-bind:items="schoolItems" />
        </li>
      </ol>
    </div>
  </div>
</template>

<script>
import PersonalInfo from './PersonalEditor'
import WorksExprience from './WorksExprience'
import SchoolEditor from './SchoolEditor'
export default {
  components:{
    PersonalInfo, WorksExprience, SchoolEditor
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
      worksExprience: [
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

