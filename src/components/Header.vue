<template>
  <header>
    <h1 @click="change">{{title}}{{tit}}</h1>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props:{
    tit:{
      type:String,
      required:true
    }
  },
  data () {
    return {
      title:"Vue.js Demo"
    }
  },
  methods:{
    change(){
      // this.tit=""
      this.$emit("changeTit","子组件向父组件传值")
    }
  }
}
</script>

<style scoped>
header{
  background-color: aquamarine;
  text-align: center;
  padding: 20px
}
</style>
