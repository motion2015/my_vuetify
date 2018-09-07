<template>
    <v-container>
        <v-alert
        :value="alert" color="lime"
        type="warning"
        >
        Please fill email and password
        </v-alert>
        <v-form @submit.prevent="submit">            
            <v-text-field
            v-model="email"
            label="E-mail"
            required
            ></v-text-field>
            <v-text-field
            v-model="password"
            type="password"
            label="Password"
            required
            ></v-text-field>
            <v-btn color="green" type="submit">Submint</v-btn>
        </v-form>
    </v-container>
</template>
<script>
export default {
    data() {
        return {
            email: null,
            password: null,
            alert: false
        }
    },
    methods: {
        submit() {
            if(!this.email && !this.password) {
                this.alert = true;
            }else {
                this.alert = false;
            }
            console.log(`Email is ${this.email} and Password is ${this.password}`)
        }
    }
}
</script>

  