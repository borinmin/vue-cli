<template>
<h1>Whose click:{{clicker}}</h1>
<ButtonCount :title="title" :user="users[0]" parent="child" v-on:handleClickCount="detectUserClick($event)"/>
<ButtonCount :user="users[1]"  v-on:handleClickCount="detectUserClick($event)"/>
<ButtonCount :user="users[2]" v-on:handleClickCount="detectUserClick($event)"/>
  <!--<img alt="Vue logo" src="./assets/logo.png">-->
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import ButtonCount from './components/ButtonCount.vue'
export default {
  name: 'App',
  components: {   
    ButtonCount
  },
  data(){
    return  {
      title:'First Vue App',
      users:['Borin','Tola', 'Dara'],
      clicker:[]
    }
  },
  methods:{
    detectUserClick(value){
      console.log(value)
      // this.clicker.prototype.filter(item=>{
      //   if(value!=item && length(this.clicker)>0){
      //     this.clicker.push(item)
      //   }
      // })
      this.clicker.push(value)
      console.log("Who clicked:",this.clicker)
    }

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
