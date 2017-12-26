<template>

    <div class="card app-todo normal" :class="{finished:todo.isFinished}">
        <div class="check-box">
            <input type="checkbox">
        </div>
        
        <div class="card-content todo-card">
            <div class="card-content-inner todo-content">{{todo.content}}</div>


                <div class="control-box">
                    <button :class="{'button-fill' :todo.isFinished}" class="button  button-small button-success"><span class="icon icon-check"></span></button>
                    <button class="button  button-small button-fill button-danger"><span class="icon icon-remove"></span></button>
                </div>
        </div>
    </div>
           
</template>

<script>
export default{
    name:'app-todo',
    props:['todo'],
    data(){
        return{
            
        }
    }   
}
</script>

<style scoped>

</style>