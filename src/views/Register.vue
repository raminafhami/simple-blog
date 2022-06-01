<template>
    <div class="register container">
        <div class="row">
            <div class="col-lg-4 mx-auto border shadow rounded p-4 mt-2">
                <h1 class="text-center m-3">register</h1>
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

                    <div class="mb-3">
                        <label for="password2" class="form-label">Repeat Password</label>
                        <input type="password" class="form-control" :class="{'is-invalid': password2E === true, 'is-valid': password2E === false}" id="password2" v-model="password2">
                        <div class="invalid-feedback" v-if="password2E">
                            {{password2EM}}
                        </div>
                    </div>
                    <button type="submit" class="btn btn-success">Register</button>
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
            password2: "",
            usernameE: null,
            passwordE: null,
            password2E: null,
            usernameEM: null,
            passwordEM: null,
            password2EM: null
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

            if (this.password2.length < 8) {
                access =  false;
                if (this.password2 == 0) {
                    this.password2E = true;
                    this.password2EM = "Repeeat Password is required";
                } else {
                    this.password2E = true;
                    this.password2EM = "Repeat Password must be at least 8 character";
                } 
            } else {
                this.password2E = false;
                this.password2EM = "";
            };

            if (this.password !== this.password2) {
                access =  false;
                this.passwordE = true;
                this.password2E = true;
                this.password2EM = "Repeat Password and Password must be same";
            }

            if (access) {
                this.$router.push("/login");
            };
        }
    }
}
</script>