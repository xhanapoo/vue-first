<template>
  <div id="home">
    <app-header v-on:titlechanged='updatetitle($event)' v-bind:title="title"></app-header>
    <users v-bind:users='users'></users>
    <app-footer v-bind:title="title"></app-footer>
  </div>
</template>

<script>
//局部注册组件
import Users from './Users'
import Header from './Header'
import Footer from './Footer'

export default {
  name: 'home',
  data(){
    return{
        title:'传递的是一个值',
        users:[]
    }
  },
  methods:{
    updatetitle(title){
      this.title= title;
    }
  },
  components:{
    'users':Users,
    'app-header':Header,
    'app-footer':Footer
  },
  created(){
      this.$http.get('http://jsonplaceholder.typicode.com/users')
      .then((data) => {
          this.users=data.body;
          
          
      })
  }
}
</script>
<style scoped>
h1{
  color: purple;
}
</style>
