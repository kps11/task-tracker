<template>
    <header>
        <h1>
            {{ title }}
        </h1>
        <Button v-show="homePage" @btn-click="$emit('toggle-add-task')"
        :name= "showAddTask ? 'Close' : 'Add Task'" 
        :color="showAddTask ? 'red' : 'green'"/>
        <!-- <Button name="Update Task" color="Blue"/>
        <Button name="Delete Task" color="Red"/> -->
    </header>
</template>

<script>
import Button from "./Button.vue"
export default {
    name : "Header",
    // props:['title'],
    props: {
        title:{
            type : String,
            default: 'Hello World'
        },
        showAddTask :{
            type: Boolean
        }
    },
    components:{
        Button
    },
    computed: {
        homePage(){
            if(this.$route.path === "/"){
                return true
            }else{
                return false
            }
        }
    }
}
</script>

<style scoped>
    header{
        display: flex;
        justify-content: space-around;
        align-items: center;
        margin-bottom: 2em;
    }
</style>