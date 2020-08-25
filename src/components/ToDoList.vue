<template>
    <div>
        <div v-for="todo in todos" :key="todo">
            <label>
            <input type="checkbox" v-model="todo.done">
            <input v-model="todo.text" v-bind:class="{donestyle:todo.done}">
            <p v-if="todo.done">お疲れさまでした！よく頑張りましたね</p>
            </label>
        </div>
        <p>追加する場合は以下に記入してください</p>
        <input type="text" v-model.trim="addtext" @keyup.enter="addtodo">
        <p><button @click="cleantodo">完了済みを削除</button></p>
        <p>{{remaining}}/{{todos.length}}件完了</p>
    </div>
</template>

<script>
export default {
    data() {
        return{ 
            addtext:'',
            todos:[
            {done:false,text:''},
            {done:false,text:''},
            {done:false,text:''}
        ]
        }
    },
    computed:{
        remaining:function(){
            return this.todos.filter(function(val){
                return val.done==true;
            }).length
        }
    },
    methods:{
        addtodo:function(){
            if(this.addtext){
                this.todos.push({done:false,text:this.addtext});
                this.addtext='';
            }
        },
        cleantodo:function(){
            this.todos=this.todos.filter(function(val){
                return val.done==false;
            })
        }
    }
}
</script>

<style>
    .donestyle{
        text-decoration: line-through;
        color: lightgray;
    }
</style>