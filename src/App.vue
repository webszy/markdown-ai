<script setup>
import 'bytemd/dist/index.css'
import { Editor } from '@bytemd/vue-next'
import frontmatter from '@bytemd/plugin-frontmatter'
import gemoji from '@bytemd/plugin-gemoji'
import gfm from '@bytemd/plugin-gfm'
const plugins = [
  gfm(),
  gemoji(),
  frontmatter()
]
const content = ref('')
</script>

<template>
  <input class="md-title" placeholder="please enter title..."/>
  <Editor class="md"
          :value="content"
          mode="split"
          :plugins="plugins"
          @change="(v)=>content=v"
  />

</template>
<style>
html,body,#app,input{
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
}
input{
 border: none;
}
.bytemd{
  width: 100%;
  height: 100%;
}
.bytemd-tippy-right:last-child{
  opacity: 0;
}
</style>
<style scoped>

.md-title{
  width: 100%;
  height: 100px;
  box-sizing: border-box;
  padding-left: 30px;
  font-size: 40px;
}
.md{
  display: flex;
  width: 100%;
  height: calc(100% - 100px);
}

</style>
