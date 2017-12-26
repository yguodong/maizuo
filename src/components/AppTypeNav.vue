<template>
    <nav class="bar bar-tab app-type-nav">
            <div  :key="_type.type" @click="changeType(_type.type)" v-for="_type in types" :class="['circle',_type.type]">
                {{_type.content}}</div>
           
        </nav>
        <!-- 点击div控制content的数据，兄弟组件间的通信，事件总线 -->
</template>

<script>
export default{
    name:'app-header',
    props:['changeType'],
    data(){
        return{
            types:[
            {type:'all',content:'A'},
            {type:'finish',content:'F'},
            {type:'unfinish',content:'U'}

        ]
        }
    }  
}
</script>

<style scoped>

</style>
