<template>
    <div class="text-green-300">You have {{completed}} completed tasks </div>
    <div class="text-red-300">You have {{unCompleted}} uncompleted tasks </div>
</template>

<script>
import {computed} from "vue"
export default {
    props : {
        todoList : Array,

    },
    setup(props){
        const completed = computed(()=> props.todoList.filter((i) => i.completed).length)
        const unCompleted = computed(()=> props.todoList.filter((i) => !i.completed).length)


        return {completed, unCompleted}
    }
}
</script>