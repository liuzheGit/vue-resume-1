<template>
  <div id="app">
    <Topbar class="topbar"></Topbar>
    <main>
      <Editor class="editor"></Editor>
      <Preview class="preview"></Preview>
    </main>
  </div>
</template>

<script>

import Topbar from './components/Topbar'
import Editor from './components/Editor'
import Preview from './components/Preview'

export default {
  name: 'App',
  components: {
    Topbar, Preview, Editor
  }
}
</script>

<style lang="scss">
html, body, #app{
  height: 100%;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  flex-direction: column;
}
.icon {
      width: 1em; height: 1em;
      vertical-align: -0.15em;
      fill: currentColor;
      overflow: hidden;
  }
main {
  display: flex;
  flex: 1;
  background-color: #DDD;
  > div {
    margin: 16px;
    box-shadow: 0 0 5px hsla(0, 0, 0, .3);
    background: #fff;
    border-radius: 4px;
    overflow: hidden;
  }
  > .editor {
    width: 30em;
  }

  > .preview {
    flex: 1;
  }
}
</style>
