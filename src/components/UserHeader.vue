<template>
    <header>
        <h1>{{title}}</h1>
        <Button @show-add-user="$emit('show-add-user')" text="Add User" color="green" />
    </header>
</template>

<script>
import Button from './Button.vue';
    export default {
        name: 'UserHeader',
        props:{
            title: String,
        },
    components: {
    Button,
}
    }
</script>

<style scoped>
    header{
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 10px;
        border: 1px solid #ccc;
        border-radius: 10px;
        margin-bottom: 10px;
    }

</style>