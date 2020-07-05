<template>
  <div id="app">
    <mylist v-bind:title="message"
    <hr>
    <div><table v-html="log" align="center" ></table></div>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
    Mylist
  },
  data:function(){
    return  {
      message:"メモを入力してください",
      list:[],
      count:0,
    };
  },
  computed:{
    log:function(){
      var table="<tr><th class=head></th></tr>";
      for(var i in this.list){
        table += "<tr><td>+this.list[i]+</td></tr>"
      }
      return table;
    }
  },
  methods:{
    appAction:function(text){
      if(this.length == 5){
        this.list.unshift(text);
        this.list.splice(5,1);
        this.count +=1;
      }else{
        this.listunshift(text);
        this.count+=1;
      }
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
