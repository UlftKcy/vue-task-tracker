<template>
    <header>
        <h1>{{title}}</h1>
        <Button title="Add Task"/>
    </header>
</template>


<script>
import Button from "./Button.vue";

export default {
    name:"Header",
    props: {
        title:{
            type:String,
            default:"Hello World"
        },
    },
    components:{
        Button,
    }
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