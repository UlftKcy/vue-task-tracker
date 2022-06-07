<template>
    <form>
        <div>
        <label for="task_name">Task Name</label>
            <input type="text" name="task_name" id="task_name">
        </div>
        <div>
         <label for="task_name">Task Date</label>
            <input type="text" name="task_date" id="task_date">
        </div>
        <div class="input-reminder">
         <label for="task_name">Reminder</label>
            <input type="checkbox" name="reminder" id="reminder">
        </div>
        <div class="btn-save">
            <Button title="Save"/>
        </div>
    </form>
</template>


<script>
import Button from "./Button.vue";

export default {
    name:"AddTask",
    components:{
        Button,
    }
}
</script>

<style scoped>

form{
    height: 50%;
    margin: 20px 20px 20px 0;
}
label{
    font-weight: bold;
    color: rgb(187, 125, 125);
}
input{
    width: 100%;
    padding: 12px 0 12px 12px;
    border: 0;
    margin-top: 5px;
    border-radius:5px ;
}
input:focus{
    outline: none;
}
.input-reminder{
    display: flex;
    align-items: center;
}
div{
    margin-bottom: 1rem;
}
.btn-save{
    display: flex;
    justify-content: flex-end;
}

</style>