<template>
    <div class="task-card" :class="[task.reminder ? 'reminder' : 'task']" @dblclick="toggleReminder(task.id)">
    <h3>
    {{task.text}}
    <i class="fas fa-times" @click="removeTask(task.id)"></i>
    </h3>
    <span>{{task.day}}</span>
    </div>
</template>
<script>
export default {
    name:"Task",
    props:{
        task:{
            type:Object,
            default:{},
        }
    },
    methods:{
        removeTask:function (id) {
            this.$emit("delete-task",id);
        },
        toggleReminder:function(id){
            this.$emit("toggle-reminder",id);
        }
    }
}
</script>

<style scoped>
.task-card{
    background-color: rgb(250, 249, 232);
    color: rgb(189, 73, 27);
    border: 1px solid #ddd;
    margin-bottom: 10px;
    padding: 5px 10px;
    border-radius: 5px;
}
h3{
    margin:10px 0;
    display: flex;
    justify-content:space-between;
    align-items: center;
}
i{
    margin-right: 0.7rem;
    cursor: pointer;
}
span{
    color: rgb(92, 90, 90);
}
.reminder{
    border-left: 5px solid rgb(189, 73, 27);

}
.task{
    border-left: 0;
}
</style>