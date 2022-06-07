<template>
<button @click="onClick()">{{title}}</button>
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
            default:"Button",
        }
    },
    methods: {
        onClick : function(){
            console.log(11)
        }
    },
}
</script>

<style scoped>
button{
    padding: 1rem 2rem;
    background-color: rgb(154, 235, 185);
    color: rgb(9, 73, 34);
    font-weight: bold;
    font-size: 0.9rem;
    border: 0;
    border-radius: 10px;
    cursor: pointer;
}
button:hover{
    background-color: rgb(9, 73, 34);
    color: #ffff;
}
</style>

