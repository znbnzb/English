<template>
    <div id="TranslateOutput">
      <h2>{{translatedText}}</h2>  <!--用插值法将数据嵌进来-->
     <h3>请翻译</h3>
    </div>
</template>

<script>
    export default {
        name:'TranslateOutput',
        props:[
            'translatedText'  //接收app根组件的翻译值
        ]
        
    }
</script>

<style scoped>

</style>