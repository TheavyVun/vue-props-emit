<template>
    <section>
        <div class="card">
            <div class="card-detail">
                <div class="card-title">
                    <h3>{{fullname}}</h3>
                </div>
                <div class="card-footer">
                    <button-view @click="toggleDetail" classbtn="detail"  :namebtn="detail ? 'Hide' : 'Detail'" />
                    <button-view @click="getFriendId" namebtn="Delete" />
                </div>
            </div>
            <hr v-if="detail" class="hr">
            <div v-if="detail" class="card-body">
                <li>Tel: {{friend.phone}}</li>
                <li>Email Address: {{friend.email}}</li>
                <li>Position: {{friend.job}}</li>
                <li>Description: {{friend.description}}</li>
            </div>

        </div>
    </section>
</template>

<script>
import Button from './ButtonView.vue'
export default {
    emits: [
        "deleted",
    ],
    components: {
        "button-view": Button,
    },
    props: {
        friend: Object,
    },
    data() {
        return {
            detail: false,
        }
    },
    methods: {
        getFriendId() {
            this.$emit('deleted', this.friend.id);
        },
        toggleDetail() {
            this.detail = !this.detail;
        }
    },
    computed: {
        fullname() {
            return this.friend.firstname.toUpperCase() + " " + this.friend.lastname.toUpperCase();
        }
    }

}
</script>

<style scoped>
    .card {
        padding: 20px;
        border-radius: 8px;
        margin-bottom: 20px;
        border-left: 4px solid #330867;
        box-shadow: rgba(0, 0, 0, 0.25) 0px 54px 55px, rgba(0, 0, 0, 0.12) 0px -12px 30px, rgba(0, 0, 0, 0.12) 0px 4px 6px, rgba(0, 0, 0, 0.17) 0px 12px 13px, rgba(0, 0, 0, 0.09) 0px -3px 5px;
        /* transform: rotate(10deg); */
    }
    .card:hover {
        box-shadow: rgba(0, 0, 0, 0.56) 0px 22px 70px 4px;

    }
    h3 {
        margin: 0;
    }
    li {
        color: #000;
        padding: 0;
        box-sizing: border-box;
    }
    .card-body {
        margin: 10px 0;
    }
    .btn {
        background-image: linear-gradient(to right, red 0%, orange 50%, #f10303 100%);
    }
    .detail {
        margin-right: 5px;
        background-image: linear-gradient(to right, #330867 0%, #06aaaa 50%, #330867 100%);
    }
    .btn:hover {
        background-image: linear-gradient(to right, orange 0%, #f10303 50%, orange 100%);
    }
    .detail:hover {
        margin-right: 5px;
        background-image: linear-gradient(to right, #06aaaa 0%, #330867 50%, #06aaaa 100%);
    }
    .card-detail {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    .hr {
        margin-top: 5px;
    }

</style>