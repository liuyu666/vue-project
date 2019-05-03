<template>
  <footer>
    <p @click="change">{{copyright}}{{tit}}</p>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  props:{
    tit:{
        type:String,
        required:true
    }
    
  },
  data () {
    return {
        copyright:"copyright 2019 5 2"
    }
  },
  methods:{
    change(){
      this.tit = ""
    }
  }
}
</script>

<style scoped>
footer{
    background-color: black;
    text-align: center;
    padding: 4px;
    color: aliceblue
}
</style>
