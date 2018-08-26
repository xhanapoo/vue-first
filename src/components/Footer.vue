<template>
  <footer v-on:click='changeTitle'>
      <p>{{copyright}}{{title}}</p>
  </footer>
</template>

<script>
export default {
  name: 'app-footer',
  props:{
    title:{
        type:String
    }
  },
  data () {
    return {
        copyright:'copyright 2017 vue Dome'
    }
  },
  methods:{
        changeTitle:function(){
            // this.title='这是底部的新增title';
            this.$emit('titlechanged','子向父组件传值');
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    footer{
        background: #222;
        padding: 6px;
    }
    p{
        color: lightgreen;
        text-align: center;
    }
</style>
