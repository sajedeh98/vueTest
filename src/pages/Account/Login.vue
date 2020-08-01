<template>
          <section class="login_part section_padding">
        <div class="container">
            <div class="row align-items-center">
                <div class="col-lg-6 col-md-6">
                    <div class="login_part_text text-center">
                        <div class="login_part_text_iner">
                            <h2>New to our Shop?</h2>
                            <p>There are advances being made in science and technology
                                everyday, and a good example of this is the</p>
                            <a href="/Login" class="btn_3">Sign in an Account</a>
                        </div>
                    </div>
                </div>
                <div class="col-lg-6 col-md-6">
                    <div class="login_part_form">
                        <div class="login_part_form_iner">
                            <h3>Welcome ! <br>
                                Please Sign up now</h3>


                                        <form action="#">
              <input type="email" placeholder="Email" v-model="email">
              <input type="password" placeholder="Password" v-model="password">
              <br>
              <br>
              <a
                class="btn btn-block submit-btn"
                @click.prevent="LoginUser()"
              >Login</a>
            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            email:"",
            password:""
        };
    },
    methods:{
        LoginUser() {
            const login = {
                email:this.email,
                password: this.password
            };
            this.$store.dispatch("LoginUser",login);
        }
    }
};
</script>
