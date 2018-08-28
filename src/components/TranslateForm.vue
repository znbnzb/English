<template>
    <div id="translateForm">
         <form v-on:submit="formSubmit">
             <input type="text" placeholder="输入需要翻译的内容">
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
        components:{
            
        }
    }
</script>

<style scoped>

</style>