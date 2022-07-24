<template>
    <div class="main">
        <h2>All Friends</h2>
        <card-view @deleted="deleteFriend" v-for="friend of friends" :key="friend" :friend="friend" />
    </div>
</template>

<script>
import CardView from './CardView.vue'
import axios from 'axios'
export default {
    components: {
        'card-view': CardView,
    },
    props: {
    },
    data() {
        return {
            friends: [
                // {firstname: "Theavy", lastname: "Vun", job: "API Developer", phone: "0889708156", email: "theavyvun@gmail.com", description: "sdfasdfsafda sadfasfdasdfThe best Player, But play min del win"},
                // {firstname: "Theavy", lastname: "Vun", job: "API Developer", phone: "0889708156", email: "theavyvun@gmail.com", description: "The best Player, But play min del win"},
                // {firstname: "Theavy", lastname: "Vun", job: "API Developer", phone: "0889708156", email: "theavyvun@gmail.com", description: "The best Player, But play min del win"},
            ]
        }
    },
    mounted() {
        this.getFriends();
    },
    methods: {
        getFriends() {
            axios.get('http://127.0.0.1:81/api/friends').then(res=> {
                this.friends = res.data;
            })            
        },
        deleteFriend(friendId)  {
            axios.delete('http://127.0.0.1:81/api/friends/' + friendId).then(res => {
                console.log(res);
                this.getFriends();
            })
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
    .main {
        width: 60%;
        box-sizing: border-box;
        text-align: center;
        padding: 20px 30px;
        height: 84vh;
        overflow: auto;
    }
    .main::-webkit-scrollbar {
        display: none;
    }

</style>