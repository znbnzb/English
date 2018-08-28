<template>
  <div id="app">
    <h1>在线翻译</h1>
    <h5>简单 / 易用 / 便捷</h5>
    <!-- 调用方法 -->
    <translateForm v-on:getform2="getText1"></translateForm>  
  </div>
</template>

<script>
import translateForm from './components/TranslateForm'
export default {
  name: 'App',
  methods:{
      getText1:function(text){
          alert(text);
      }
  },
  components:{
      translateForm
  }
}
</script>

<style>
#app {
  
}
</style>
