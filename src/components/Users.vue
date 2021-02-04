<template>
    <div class="container">
        <h1>
            Daftar Nama User
        </h1>
        <div class="list">
            <ul v-for="user in users" :key="user.id">
                <li>
                    <router-link :to="{name : 'User', params: {id:user.id}}">
                        {{ user.name }}
                    </router-link>
                </li>
            </ul>
        </div>
    </div>
</template>
<script>
import axios from 'axios'

export default {
    name : 'Users',
    data() {
        return {
            users : []
        }
    },
    created(){
        this.getAllusers()
    },
    methods : {
        getAllusers() {
            axios.get('https://jsonplaceholder.typicode.com/users')
            .then((response) => {
                this.users = response.data;     
            })
            .catch((err) => {
                console.log(err);
            })
        }
    }
}
</script>

<style scoped>
    .list{
        margin-left: -50px;
    }
</style>