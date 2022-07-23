<template>
    <form>
        <h2>Add Friend</h2>
        <div class="fullname">
            <input-view v-model="firstname" valuemodel="firstname" :value="firstname" @input="firstname = $event" typeinput="text" sms="firstname" />
            <input-view v-model="lastname" valuemodel="lastname" :value="lastname" @input="lastname = $event" classinput="ml" typeinput="text" sms="lastname" />
        </div>
        <div class="contact">
            <input-view v-model="email" valuemodel="email" :value="email" @input="email = $event" typeinput="email" sms="Email Address" />
            <input-view v-model="phone" valuemodel="phone" :value="phone" @input="phone = $event" classinput="ml" typeinput="text" sms="Phone Number" />
        </div>
        <input-view v-model="job" valuemodel="job" :value="job" @input="job = $event" typeinput="text" sms="Position" />
        <input-view v-model="description" valuemodel="description" :value="description" @input="description = $event" typeinput="text" sms="Description" />
        <button-view @click="addFriend" namebtn="Add" typebtn="submit" />
    </form>
</template>

<script>
import InputView from './InputView.vue'
import Button from './ButtonView.vue'
import axios from 'axios'
export default {
    components: {
        'input-view': InputView,
        'button-view': Button
    },
    props: {
    },
    data() {
        return {
            firstname: '',
            lastname: '',
            job: '',
            phone: '',
            email: '',
            description: '',
        }
    },
    methods: {
        addFriend() {
            let friend = {
                firstname: this.firstname,
                lastname: this.lastname,
                job: this.job,
                phone: this.phone,
                email: this.email,
                description: this.description,
            };
            axios.post('http://127.0.0.1:81/api/friends', friend).then(res=> {
                console.log(res);
                this.firstname = '';
                this.lastname = '';
                this.job = '';
                this.phone = '';
                this.email = '';
                this.description = '';
            })
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    form {
        width: 90%;
        margin: auto;
        padding: 20px;
        border-radius: 10px;
        box-shadow: rgba(0, 0, 0, 0.25) 0px 54px 55px, rgba(0, 0, 0, 0.12) 0px -12px 30px, rgba(0, 0, 0, 0.12) 0px 4px 6px, rgba(0, 0, 0, 0.17) 0px 12px 13px, rgba(0, 0, 0, 0.09) 0px -3px 5px;
        background-image: linear-gradient(to right, #30cfd0 0%, #330867 100%);
    }
    form:hover {
        background-image: linear-gradient(to left, #30cfd0 0%, #330867 100%);

    }
    h2 {
        text-align: center;
        text-decoration: underline;
        text-decoration-style: double;
        margin-bottom: 20px;
        text-shadow: 5px 5px 20px #000;
        color: #fff;
    }
    .btn {
        border: 1px solid rgb(247, 222, 222);
        background-image: linear-gradient(to left, #30cfd0 0%, #330867 100%);       
    }
    .btn:hover {
        background-image: linear-gradient(to right, #30cfd0 0%, #330867 100%);       

    }
    .fullname, .contact {
        display: flex;
    }
</style>