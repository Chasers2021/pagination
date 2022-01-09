<template>
    <div class="input">
        <input type="text" v-model="title"/>
        <button @click= "add">添加</button>
    </div>
</template>
<script>
// import bus from './bus'
export default {
    data(){
        return {
            title:''
        }
    },
    methods:{
        add(){
            this.$emit('add',this.title)
        },
       
    },
  
    
}
</script>
<style lang="scoped">
    
</style>