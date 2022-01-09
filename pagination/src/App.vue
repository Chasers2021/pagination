<template>
  <div id="app" ref="app">
    <myinput @add="add"></myinput>
    <list :list="list" :current="current" @delItem="delItem"></list>
    <Pagination :total="list.length" :pageSize="pageSize" @change="changePagination" ref="pagination"></Pagination>
  </div>
</template>

<script>
import list from "./components/list";
import myinput from "./components/input";
import Pagination from "./components/pagination";
export default {
  name: "App",
  components: {
    list,
    myinput,
    Pagination,
  },
  data() {
    return {
      current:1,
      pageSize:5,
      list: [
        {
          id: 1,
          title: "内容1(点击我即可删除)",
        },
        {
          id: 2,
          title: "内容2(点击我即可删除)",
        },
        {
          id: 3,
          title: "内容3(点击我即可删除)",
        },
        {
          id: 4,
          title: "内容4(点击我即可删除)",
        },
        {
          id: 5,
          title: "内容5(点击我即可删除)",
        },
        {
          id: 6,
          title: "内容6(点击我即可删除)",
        },
        {
          id: 7,
          title: "内容7(点击我即可删除)",
        },
        {
          id: 8,
          title: "内容8(点击我即可删除)",
        },
        {
          id: 9,
          title: "内容9(点击我即可删除)",
        },
        {
          id: 10,
          title: "内容10(点击我即可删除)",
        },
        {
          id: 11,
          title: "内容11(点击我即可删除)",
        },
      ],
    };
  },
  computed: {},
  created() {
    window.myData = this;
    console.log(this)
  },
  methods: {
    add(title) {
      this.list.push({
        id: this.list.length + 1,
        title,
      });
    },
    delItem(id) {
      this.list.forEach((value,index)=>{
          if(id === value.id){
            this.list.splice(index,1)
          }
      })
      this.current = Math.ceil(this.list.length/this.pageSize)
    },
    changePagination (current) {
      this.current = current
    }
  },
  watch: {
    // list: {
    //   handler: function (val, oldVal) {
    //     console.log(val.length, oldVal);
    //     this.total = val.length;
    //   },
    //   deep: true,
    //   immediate: true,
    // },
  },
};
</script>

<style>
</style>
