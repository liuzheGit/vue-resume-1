<template>
  <div id="editor">
    <div class="menu">
      <ol>
        <li class="active">
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-credentials_icon"></use>
          </svg>
        </li>
        <li>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-workyear"></use>
          </svg>
        </li>
        <li>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-book"></use>
          </svg>
        </li>
        <li>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-project"></use>
          </svg>
        </li>
        <li>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-jiangbei-"></use>
          </svg>
        </li>
        <li>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-phone"></use>
          </svg>
        </li>
        <li>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-xingxing1"></use>
          </svg>
        </li>
      </ol>
    </div>
    <div class="editor-content">
      ners
    </div>
  </div>
</template>

<style lang="scss">
  #editor {
    border: 1px solid black;
    min-height: 100px;
    display: flex;
    > div {
      border: 1px solid;
    }
    .menu{
      border-color: red;
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
    }
  }
</style>

