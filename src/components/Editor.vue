<template>
  <div id="editor">
    <div class="menu">
      <ol>
        <li v-bind:class="{active: currentTab === 0}" v-on:click="currentTab=0">
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-shenfenzhenghao"></use>
          </svg>
        </li>
        <li v-bind:class="{active: currentTab === 1}" v-on:click="currentTab=1">
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-workfillmtui"></use>
          </svg>
        </li>
        <li v-bind:class="{active: currentTab === 2}" v-on:click="currentTab=2">
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-book"></use>
          </svg>
        </li>
        <li v-bind:class="{active: currentTab === 3}" v-on:click="currentTab=3">
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-code"></use>
          </svg>
        </li>
        <li v-bind:class="{active: currentTab === 4}" v-on:click="currentTab=4">
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-icon22"></use>
          </svg>
        </li>
        <li v-bind:class="{active: currentTab === 5}" v-on:click="currentTab=5">
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-phone"></use>
          </svg>
        </li>
      </ol>
    </div>
    <div class="editor-content">
      <ol>
        <li v-bind:class="{active: currentTab === 0}">tab1</li>
        <li v-bind:class="{active: currentTab === 1}">tab2</li>
        <li v-bind:class="{active: currentTab === 2}">tab3</li>
        <li v-bind:class="{active: currentTab === 3}">tab4</li>
        <li v-bind:class="{active: currentTab === 4}">tab5</li>
        <li v-bind:class="{active: currentTab === 5}">tab6</li>
      </ol>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      currentTab: 0
    }
  }
}
</script>


<style lang="scss">
  #editor {
    min-height: 100px;
    display: flex;
    > div {
      border: 1px solid;
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
      li {
        display: none;
        &.active{
          display: block;
        }
      }
    }
  }
</style>

