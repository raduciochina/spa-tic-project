<template>
    <div class="user">
        <h3>{{user.name}}</h3>
        <p>{{user.email}}</p>
        <i @click="$emit('delete-user', user.id)" class="fas fa-times"></i>
        <i class="fas fa-info"></i>
    </div>
</template>
<script>
export default{
    name: 'User',
    props: {
        user: Object,
    },
}
</script>

<style scoped>
.user{
    border: 1px solid #ccc;
    border-radius: 10px;
    padding: 10px;
    margin-bottom: 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.user h3{
    margin: 0;
}
.user p{
    margin: 0;
}
.fa-times{
    color: red;
    cursor: pointer;
}
.fa-info{
    color: blue;
    cursor: pointer;
}


</style>