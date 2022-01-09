<template>
  <div class="list">
    <li v-for="item in currentList" :key="item.id" @click="delItem(item.id)">
      {{ item.title }}
    </li>
  </div>
</template>
<script>
// import bus from "./bus";
export default {
  props: {
    list: Array,
    current:Number
  },
  data(){
    return {
    }
  },
  computed:{
      currentList:{
        get:function(){
     
          return this.list.slice(this.current*5-5,this.current*5)
        }
      }
  },
  methods: {
    addTitle(title) {
      console.log(title);
    },
    delItem(id){
      this.$emit('delItem',id)
    },
   
  },
  watch:{
    
    },
    created(){
    },
  mounted() {

  },
  beforeDestroy(){

  },
 
};
</script>
<style scoped>
  .list{
    list-style: none;
  }
  li {
    cursor: pointer;
  }
</style>
