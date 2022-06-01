<template>
    <div class="login container">
        <div class="row">
            <div class="col-lg-4 mx-auto border shadow rounded p-4 mt-2">
                <h1 class="text-center m-3">login</h1>
                <form @submit.prevent="doLogin">
                    <div class="mb-3">
                        <label for="username" class="form-label">Username</label>
                        <input type="text" class="form-control" :class="{'is-invalid': usernameE === true, 'is-valid': usernameE === false}" id="username" v-model="username">
                        <div class="invalid-feedback" v-if="usernameE">
                            {{usernameEM}}
                        </div>
                    </div>
                    
                    <div class="mb-3">
                        <label for="password" class="form-label">Password</label>
                        <input type="password" class="form-control" :class="{'is-invalid': passwordE === true, 'is-valid': passwordE === false}" id="password" v-model="password">
                        <div class="invalid-feedback" v-if="passwordE">
                            {{passwordEM}}
                        </div>
                    </div>
                    <button type="submit" class="btn btn-success">Login</button>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Login",
    data() {
        return {
            username: "",
            password: "",
            usernameE: null,
            passwordE: null,
            usernameEM: null,
            passwordEM: null
        }
    },
    methods: {
        doLogin() {
            let access =  true;
            if (this.username.length < 5) {
                access =  false;
                if (this.username == 0) {
                    this.usernameE = true;
                    this.usernameEM = "Username is required";
                } else {
                    this.usernameE = true;
                    this.usernameEM = "Username must be at least 5 character";
                } 
            } else {
                this.usernameE = false;
                this.usernameEM = "";
            };

            if (this.password.length < 8) {
                access =  false;
                if (this.password == 0) {
                    this.passwordE = true;
                    this.passwordEM = "Password is required";
                } else {
                    this.passwordE = true;
                    this.passwordEM = "Password must be at least 8 character";
                } 
            } else {
                this.passwordE = false;
                this.passwordEM = "";
            };

            if (access) {
                this.$store.commit("login", `${this.username}:${this.password}`);
                this.$router.push("/profile");
            };
        }
    }
}
</script>