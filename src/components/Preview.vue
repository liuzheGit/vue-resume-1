<template>
  <div id="preview">
    <h1>{{resumer.personalInfo.name}}</h1>
    <p>{{resumer.personalInfo.city}} | {{resumer.personalInfo.birth}}</p>
    <ul>
      <li v-for="(item, index) in resumer.workItems" :key="index">
        <p>{{item.name}}</p>
        <p>{{item.content}}</p>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  props:['resumer']
}
</script>


<style>
  #preview {
    min-height: 100px;
    /* background-color:  */
  }
</style>

