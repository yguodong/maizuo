<template>
    <div class="content app-content">
            <!-- <p v-if="showTodos.length==0">留言板上还什么都没有呢！快留下你的足迹吧</p> -->
            <AppTodo :key="todo.id" v-for="todo in showTodos" :todo='todo'></AppTodo>
        </div>   
</template>

<script>
import AppTodo from './AppTodo'
export default{
    name:'app-content',
    props:['showType'],
    data(){
        return{
            aaa:JSON.parse(localStorage.todos?localStorage.todos:'[]'),//在新增todo的时候创建id

        //todos:JSON.parse(localStorage.todos?localStorage.todos:'[]'),
        todos:[
            {id:1,content:"好心痛",isFinished:false},
            {id:2,content:"给你一碗心灵鸡汤，早点休息吧",isFinished:true}
        ],
         //showType:"finish",
        // types:[
        //     {type:'all',content:'A'},
        //     {type:'finish',content:'F'},
        //     {type:'unfinish',content:'U'}

        // ],
        // isInsertShow:false,//控制弹出层显示隐藏的
        // newmsg:'',//绑定textarea,获取文本内容的
        // isSelect:false//控制复选框的显示隐藏
        }
    },
    computed:{
        //完成的数据
        upDown:function(){
            //遍历所有数据
            //如果数据的isFinished为true,则存入数组arr
            var arr=[]
            this.todos.forEach((todo)=>{
                if(todo.isFinished){
                    arr.push(todo)
                }
            })
            return arr
        },
        unDown:function(){
            var arr=[]
            this.todos.forEach((todo)=>{
                if(!todo.isFinished){
                    arr.push(todo)
                }
            })
            return arr
        },
        //显示页面
        showTodos:function(){
            //通过switch判断showType执行哪个函数
            switch(this.showType){
                case 'all':return this.todos;break;
                case 'finish':return this.upDown;break;
                case 'unfinish':return this.unDown;break;
                default :return this.todos;break;

            }
        }
    },
    components:{AppTodo}   
}
</script>

<style scoped>

</style>
