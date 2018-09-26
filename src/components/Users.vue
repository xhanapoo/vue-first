<template>
  <div class="users">
      <h2>这里是Users内容</h2>
      <ul>
          <li v-for="user in users">
              <h4>{{user.name}}</h4>
              <h3>{{user.email}}</h3>
          </li>
      </ul>
      <button v-on:click='deletUser'>删除</button>
  </div>
</template>

<script>
export default {
  name: 'users',
  props:{
      users:{
          type:Array,
          required:true
      },
  },
  data () {
    return {
       
    }
  },
  methods:{
      deletUser:function(){
          this.users.pop();
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h2{
    text-align: center;
}
.users{
    width: 100%;
    max-width: 1200px;
    margin:40px auto;
    padding: 0 20px;
    box-sizing: border-box;
}
ul{
    display: flex;
    flex-wrap: wrap;
    list-style-type: none;
    padding: 0;
}
li{
    flex-grow: 1;
    flex-basis: 200px;
    text-align: center;
    border:1px solid #222;
    margin:10px;
}
</style>
