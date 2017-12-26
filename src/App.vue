<template>
  <div id="app">
    <!-- 组件注册 -->
    <AppHeader/>
    <AppContent :showType="showType"/>
    <AppTypeNav :changeType="changeType"/>
  </div>
</template>

<script>
//组件引入
import AppHeader from './components/AppHeader'
import AppContent from './components/AppContent'
import AppTypeNav from './components/AppTypeNav'
export default {
  name: 'app',
  data:function(){
    return{
      showType:'unfinish',
    }
  },
  methods:{
      changeType(type){
          this.showType=type
      }
  },

  components: {
   // 组件注册
    AppHeader,AppContent,AppTypeNav
  }
}
</script>

<style>
/* 页面显示信息 */
.todo-content.card-content-inner{
    width:80%;
    height:5rem;
}
.card-content.todo-card{
    display:flex;
}
.card-content.todo-card .control-box{
    flex-grow:1;
    display:flex;
    flex-direction: column;
    justify-content:space-around;
    align-items:center;
}

.finished{
    border:1px solid rgb(42, 219, 66);
    
}

.content{
    padding-bottom:2.5rem;
}

/* 底层固定按钮 */
nav{display:flex;justify-content: space-around}
.circle{
    width:2rem;height:2rem;border-radius:50%;text-align:center;line-height:2.5rem;
}
.circle.all{
    background:#fff;
    color:blue;
    border:1px solid blue; 
}
.circle.all.active{
    background:blue;
    color:#fff;
}
.circle.finish{
    background:#fff;
    color:red;
    border:1px solid red; 
}
.circle.finish.active{
    background:red;
    color:#fff;
}
.circle.unfinish{
    background:#fff;
    color:yellowgreen;
    border:1px solid yellowgreen
}
.circle.unfinish.active{
    background:yellowgreen;
    color:#fff;
}


/* 信息输入 */
.mark{
    position:absolute;
    width:100%;
    height:100vh;
    z-index:999;
    background:rgba(0,0,0,0.2);
    display: flex;justify-content: center;align-items:center;
}

.insert-box{
    width:80%;
    height:15rem;
    background:#fff;
    border-radius:0.5rem;
    
    display: flex;flex-direction:column;align-items:center;justify-content: space-around
}
.insert-box .btn-box{
    width:70%;
    display: flex;justify-content: space-around;
}
.insert-box textarea{
    width:80%;
    height:50%;
    border:1px solid rgb(224,224,224)
}
/* 复选框 */

.card.normal .todo-card{
    width:100%;
}
.card.normal .check-box{
    display:none;
}


.select.card{
    display:flex;align-items: center;
}
.select.card .todo-card{
    width:90%;
}
.check-box{
    width:10%;
    display:flex;justify-content: center;align-items:center;
}
</style>
