<template>
    <div id="translateForm">
         <form v-on:submit="formSubmit">
                
             <input type="text" v-model="textToTranslate23" placeholder="输入需要翻译的内容" >
             <select>
                 <option value="en">English</option>
             </select>
             <input type="submit" value="翻译">
         </form>
    </div>
</template>

<script>
    export default {
        name:'translateForm',
        data:function(){
            return {
                textToTranslate:''  //属性绑定 获取用户输入的内容
            }
        },
        methods:{
            formSubmit:function(e){
                // alert(this.textToTranslate);  

                e.preventDefault();  // 取消默认事件
                this.$emit("getform2",this.textToTranslate23) //事件注册，默认一个参数，默认注册的事件，其他事实参
                 
            }
        },
        components:{
            
        }
    }
</script>

<style scoped>

</style>