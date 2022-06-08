<template>
    <header>
        <h1>{{title}}</h1>
        <Button @toggle-add-task = "$emit('toggle-add-task')" :title="showAddTask ? 'Cancel' : 'Add Task'" :color="showAddTask ? 'red' : 'green'"/>
    </header>
</template>
<script>
import Button from "./Button.vue";

export default {
    name:"Header",
    props: {
        title:{
            type:String,
            default:"Hello World",
        },
        showAddTask:Boolean,
    },
    components:{
        Button,
    },
}
</script>

<style scoped>
header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}
h1{
    color: rgb(216, 99, 99);
}
</style>