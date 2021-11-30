<template>
    <div>
        <ul>
            <Todoitem 
            v-for="todo in todos" 
            :key="todo.title"
            :todo="todo.title"
            v-on:todo-item-changed="Changed"
            />
            {{ this.todo.title }}
            </li>
        </ul>
    </div>
</template>

<script>
import Todoitem from '/Todoitem.vue'
export default {
    props:['todos'],
    components: Todoitem,
    methods: {
        Changed(e){
            this.$emit('todos.changed',{
                original:this.todo.title,
                new:this.text
            })
        }
    },

    
}
</script>