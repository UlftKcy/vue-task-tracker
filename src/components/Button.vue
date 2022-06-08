<template>
<button @click="toggleAddTask" :style="{'background-color':color}">{{title}}</button>
</template>

<script>
export default {
    name:"Button",
    props:{
        color:{
            type:String,
            default:"black",
        },
        title:{
            type:String,
            default:"Button"
        }
    },
    methods:{
        toggleAddTask(){
            this.$emit("toggle-add-task")
        }
    }
}
</script>

<style scoped>
button{
    padding: 1rem 2rem;
    color: #ffff;
    font-weight: bold;
    font-size: 0.9rem;
    border: 0;
    border-radius: 10px;
    cursor: pointer;
}
</style>

