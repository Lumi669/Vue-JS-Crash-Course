<template>
    <header>
        <h1> {{title}}</h1>
        <Button text="Add Task" color="green"/>
    </header>
</template>

<script>
import Button from './button'

export default {
    name: 'Header',
    props: {
        title:String, 
    },
    components: {
            Button,
    }
        
    
}
</script>

// scope means that the style only applies to current component
<style scope>
Header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
    color: rgb(51, 153, 136);
}
</style>
