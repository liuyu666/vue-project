<template>
  <div id="app">
    <app-header :tit="tit" @changeTit="updataTit($event)"></app-header>
    <users :list="list"></users>
    <users :list="list"></users>
    <app-footer :tit="tit"></app-footer>
  </div>
</template>

<script>
import Users from "./Users"
import Header from "./Header"
import Footer from "./Footer"

export default {
  name: 'App',
  data(){
    return {
      list:[
        //   {id:"0",name:"tom",position:"前端开发",show:false},
        //   {id:"1",name:"tom",position:"前端开发",show:false},
        //   {id:"2",name:"tom",position:"前端开发",show:false},
        //   {id:"3",name:"tom",position:"前端开发",show:false},
        //   {id:"4",name:"tom",position:"前端开发",show:false},
        //   {id:"5",name:"tom",position:"前端开发",show:false},
        //   {id:"6",name:"tom",position:"前端开发",show:false},
        //   {id:"7",name:"tom",position:"前端开发",show:false},
        //   {id:"8",name:"tom",position:"前端开发",show:false},
        //   {id:"9",name:"tom",position:"前端开发",show:false},
        //   {id:"10",name:"tom",position:"前端开发",show:false}
          ],
          tit:"增加小标题"
    }
  },
  methods:{
    updataTit(e){
      this.tit = e;
    }
  },
  components: {
      "app-header":Header,
      "users":Users,
      "app-footer":Footer
  },
  created(){
      this.$http.get("http://jsonplaceholder.typicode.com/users")
      .then((data)=>{
          this.list = data.body;
          console.log(data)
      })
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>