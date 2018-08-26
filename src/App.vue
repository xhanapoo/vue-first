<template>
  <div id="app">
    <app-header v-on:titlechanged='updatetitle($event)' v-bind:title="title"></app-header>
    <users v-bind:users='users'></users>
    <app-footer v-bind:title="title"></app-footer>
  </div>
</template>

<script>
//局部注册组件
import Users from './components/Users'
import Header from './components/Header'
import Footer from './components/Footer'

export default {
  name: 'App',
  data(){
    return{
      users:[
            {name:'家庭组件',position:'web开发',show:false},
            {name:'Henry',position:'web开发',show:false},
            {name:'Henry',position:'web开发',show:false},
            {name:'Henry',position:'web开发',show:false},
            {name:'Henry',position:'web开发',show:false},
            {name:'Henry',position:'web开发',show:false},
            {name:'Henry',position:'web开发',show:false},
            {name:'Henry',position:'web开发',show:false},
            {name:'Henry',position:'web开发',show:false},
            {name:'Henry',position:'web开发',show:false},
            {name:'Henry',position:'web开发',show:false},
            {name:'Henry',position:'web开发',show:false},
            {name:'Henry',position:'web开发',show:false}
        ],
        title:'传递的是一个值'
    }
  },
  methods:{
    updatetitle(title){
      this.title=title;
    }
  },
  components:{
    'users':Users,
    'app-header':Header,
    'app-footer':Footer
  }
}
</script>
<style scoped>
h1{
  color: purple;
}
</style>
