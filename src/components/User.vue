<template>
    <div class="container">
        <header>
            <h2>Detail User dengan Nama : {{ user.name }}</h2>
            
        </header>
        <ul>
            <li>Username : {{ user.username }}</li>
            <li>Email : {{ user.email }}</li>
            <li>Phone : {{ user.phone }}</li>

        </ul>
        <router-link to="/users">Back</router-link>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    name :'User',
    data(){
        return {
            user : []
        }
    },
    created(){
        this.getUser();
    },
    methods : {
        getUser(){
            const user_id = this.$route.params.id;
            axios.get(`https://jsonplaceholder.typicode.com/users/${user_id}`)
            .then((response) => {
                this.user = response.data;
            })
            .catch((err) => {
                console.log(err);
            })
        }
    }
}
</script>

<style scoped>
ul li {
    list-style: none;
}
</style>