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
        <li v-for="i in [0, 1, 2, 3, 4, 5]" v-bind:key="i"
            v-bind:class="{active: currentTab === i}">
            tab{{i}}
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
      icons: ['shenfenzhenghao', 'workfillmtui', 'book', 'code', 'icon22', 'phone']
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

