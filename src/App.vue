<template>
  <div id="app">
    <h1>在线翻译</h1>
    <h5>简单 / 易用 / 便捷</h5>
    <!-- 调用方法 -->
    <translateForm v-on:getform2="getText1"></translateForm>  
    <!-- 用v-text进行传值 -->
    <translateOutput v-text="translatedText2"></translateOutput>  
  </div>
</template>

<script>
import translateForm from './components/TranslateForm'  //调用组件
import translateOutput from './components/TranslateOutput'

export default {
  name: 'App',
  data:function(){   //接收翻译好的文本
       return{
            translatedText2:''    //接收文本
       } 
  },
  methods:{
      getText1:function(text,language){
          // alert(text);
          //用get方法，创建一个Http请求，里面的参数是请求的接口，拼上对应的参数,key 和对应的翻译语音 lang=en ，text需要翻译的文本.then 会给一个返回值
          this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180828T043035Z.4c07da35d4573c55.f0c57fcde4254c5697b5aeedcb2144741c93eb8f&lang='+language+'&text='+text)
          .then((response)=>{
            // console.log(response.body.text[0]);
            this.translatedText2 = response.body.text[0];   //将返回的值存起来，在data里面接收
          })  
      }
  },
  components:{
      translateForm,translateOutput
  }
}
</script>

<style>
#app {
  
}
</style>
