<template>
  <div class="users">
      <ul>
          <li v-for="item in list" :key="item.id">
            <h2>{{item.name}}</h2>
            <h3>{{item.email}}</h3>
          </li>
      </ul>
      <button @click="change">删除</button>
  </div>
</template>

<script>
export default {
  name: 'Users',
  props:["list"],
  data () {
    return {   
    }
  },
  methods:{
    change(){
      this.list.pop()
    }
  }
}
</script>

<style scoped>

.users{
  max-width: 1200px;
  margin: 20px auto;
  padding: 0 20px;
  box-sizing: border-box  
}
ul{
  display: flex;
  flex-wrap: wrap;
  padding: 0;
  list-style: none
}
li{
  text-align: center;
  flex-grow: 1;
  flex-basis: 200px;
  border: 1px solid rgb(248, 139, 36);
  margin: 20px;
}
</style>
