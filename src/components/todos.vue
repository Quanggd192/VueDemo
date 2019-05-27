<template>
    <div>
        <h1>Todo: </h1>
        <div v-bind:key="item.id" v-for="item in todos">
            <TodoItem v-bind:todo="item" v-on:deleteTodo="$emit('del-todo',item.id)"/>
        </div>
    </div>    
</template>

<script>
import TodoItem from './TodoItem.vue'

export default {
    name: "Todos",
    props: ["todos"],
    components:{
        TodoItem
    }
}
</script>

<style scoped>

</style>

