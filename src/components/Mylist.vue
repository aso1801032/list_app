<template>
    <div class="hello">
        <h1>{{message}}</h1>
        <div>
            <input type="text" v-model="text">
            <button v-on:click="doAction">クリック</button>
        </div>          
    </div>
    
</template>

<script>
    export default{
        name:"list",
        props:{
            title:String,
        },
        data:function(){
            return {
                message:"メモを入力してください",
                text:"",
            };
        },
        methods:{
            doAction:function(){
                var text = this.text;
                
                this.$emit("event",text);
            }
        }
    }
</script>
