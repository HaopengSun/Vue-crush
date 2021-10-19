<template>
    <h3 @dblclick="$emit('toggle-reminder', task.id)">{{ task.text }}</h3>
    <p>{{ task.day }}  {{task.reminder}}</p>
    <button @click="ondelete(task.id)">Delete</button>
</template>

<script>
export default {
    name: "Task",
    props: {
        task: Object
    },
    methods: {
        ondelete(id){
            this.$emit('delete-task', id)
        }
    }
}
</script>
