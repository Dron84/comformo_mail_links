<template>
    <div>
        <h3>Your link is no longer available<br>
            Enter email to generate a new one</h3>
        <div class="input_group">
            <input id="email" type="email" v-model="user.email" tabindex="1" required autofocus @keyup="chEmail">
            <label for="email">Email</label>
        </div>
        <div class="centrize">
            <button class="button" :disabled="dis" @click.prevent="ClickButton">generate a new one</button>
        </div>

    </div>
</template>

<script>
    export default {
        name: "newlink",
        data(){
            return{
                user: {
                    email: '',
                },
                dis: true,
            }
        },
        props: {
            checkemail:{
                type: String,
                default: '',
            },
        },
        methods:{
            chEmail(){
                if(this.checkemail==this.user.email){
                    this.dis=false
                }else{
                    this.dis=true
                }
            },
            ClickButton(){
                this.$emit('buttonClick','click')
            }
        }
    }
</script>