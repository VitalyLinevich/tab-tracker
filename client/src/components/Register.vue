<template>
    <div>
        <h1>Register Page</h1>
        <div>
            <label for="email_input">Email</label><br>
            <input type="email" name="email" v-model="email" placeholder="email" id="email_input"/>
        </div>
        <div>
            <label for="pass_input">Password</label><br>
            <input type="password" name="password" v-model="password" placeholder="password" id="pass_input"/>
        </div>
        <button @click="register()">Register</button>
    </div>
</template>

<script>

    import AuthenticationService from '@/services/AuthenticationService';

    export default {
        name: "Register",
        data() {
            return {
                email: '',
                password: '',
            }
        },
        methods: {
            async register () {
                const response = await AuthenticationService.register({
                    email: this.email,
                    password: this.password
                });
                console.log(response.data);
            }
        }
    }
</script>

<style scoped>

</style>