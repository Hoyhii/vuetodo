<template>
    <div>
        <ul>
            <Todoitem 
            v-for="todo in todos" 
            :key="todo.title"
            :todo="todo"
            v-on:todo-item-changed="Changed"
            />
        </ul>
    </div>
</template>

<script>
import Todoitem from './item.vue'
export default {
    props:['todos'],
    components: {Todoitem},
    methods: {
        Changed(e){
            this.$emit('todos.changed',e)
        }
    },

    
}
</script>