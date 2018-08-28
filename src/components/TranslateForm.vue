<template>
    <div class="row" id="translateForm">
        <div class="col-md-6 col-md-offset-3">
            <form id="transForm" class="well form-inline" v-on:submit="formSubmit">
                <input class="form-control" type="text" v-model="textToTranslate" placeholder="输入需要翻译的内容" >
                <select class="form-control" v-model="language">  <!--language获取选中的值-->
                    <option value="en">英语</option>
                    <option value="ru">俄语</option>
                    <option value="ko">韩语</option>
                    <option value="ja">日语</option>
                </select>
                <input class="btn btn-primary" type="submit" value="翻译">
            </form>
        </div>
    </div>
</template>

<script>
    export default {
        name:'translateForm',
        data:function(){
            return {
                textToTranslate:'',  //属性绑定 获取用户输入的内容
                language:''
            }
        },
        methods:{
            formSubmit:function(e){
                // alert(this.textToTranslate);  

                e.preventDefault();  // 取消默认事件
                this.$emit("getform",this.textToTranslate,this.language) //事件注册，默认一个参数，默认注册的事件，其他事实参
                 
            }
        },
        created:function(){
           this.language='en';
        }
    }
</script>

<style scoped>
#transForm{
    border:1px #ccc solid;
    border-radius: 10px;
}
</style>