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
                            <!-- <form class="row contact_form" action="#">
                                <div class="col-md-12 form-group p_star">
                                    <input type="text" class="form-control" v-model="name"
                                        placeholder="Name">
                                </div>
                                <div class="col-md-12 form-group p_star">
                                    <input type="text" class="form-control" v-model="family"
                                        placeholder="Family">
                                </div>
                                <div class="col-md-12 form-group p_star">
                                    <input type="text" class="form-control" 
                                        v-model="email"
                                        @input="$v.email.$touch()"
                                        :class="{invalid:$v.email.$error}"
                                        placeholder="Email">
                                </div>
                                  <p class="text-danger" v-if="!$v.email.email">ایمیل وارد شده معتبر نمیباشد</p>
                                  <p class="text-danger" v-if="!$v.email.sameAs && $v.email.$dirty">ایمیل وارد شده تکراری میباشد</p>
                                  <p
                                    class="text-danger"
                                    v-if="!$v.email.required && $v.email.$dirty"
                                  >لطفا ایمیل را وارد کنید</p>
                                  <p
                                    class="text-danger"
                                    v-if="!$v.email.maxLength"
                                  >ایمیل کاربر نمیتواند بیشتر از {{$v.email.$params.maxLength.max}} کاراکتر داشته باشد</p>

                                <div class="col-md-12 form-group p_star">
                                    <input type="password" class="form-control" 
                                        v-model="password"
                                        @blur="$v.password.$touch()"
                                        :class="{invalid:$v.password.$error}"
                                        placeholder="Password">
                                </div>
                                  <p
                                    class="text-danger"
                                    v-if="!$v.password.required && $v.password.$dirty"
                                  >لطفا کلمه عبور را وارد کنید</p>

                                  <p
                                    class="text-danger"
                                    v-if="!$v.password.minLength"
                                  >کلمه عبور باید حداقل شمال {{$v.password.$params.minLength.min}} کاراکتر باشد</p>

                                 <div class="col-md-12 form-group p_star">
                                    <input type="repassword" class="form-control" 
                                    placeholder="RePassword"
                                      v-model="rePassword"
                                      @input="$v.rePassword.$touch()"
                                      :class="{invalid:$v.rePassword.$error}">
                                  </div>

                                    <p
                                      class="text-danger"
                                      v-if="!$v.rePassword.sameAs && $v.rePassword.$dirty"
                                    >کلمه عبور مغایرت دارد</p>

                                <div class="col-md-12 form-group">
                                    <div class="creat_account d-flex align-items-center">
                                        <input type="checkbox" id="f-option" name="selector">
                                        <label for="f-option">Remember me</label>
                                    </div>
                                    <a @click.prevent="RegisterUser()"
                                      class="btn btn-success btn-block"
                                      :disabled="$v.$invalid">
                                        log in
                                    </a>
                                </div>
                            </form> -->

                                        <form action="#">
              <input type="text" placeholder="Name" v-model="name">
              <input type="text" placeholder="Family" v-model="family">

              <input
                type="text"
                placeholder="Email"
                v-model="email"
                @input="$v.email.$touch()"
                :class="{invalid:$v.email.$error}"
              >
              <p class="text-danger" v-if="!$v.email.email">ایمیل وارد شده معتبر نمیباشد</p>
               <p class="text-danger" v-if="!$v.email.sameAs && $v.email.$dirty">ایمیل وارد شده تکراری میباشد</p>
              <p
                class="text-danger"
                v-if="!$v.email.required && $v.email.$dirty"
              >لطفا ایمیل را وارد کنید</p>
              <p
                class="text-danger"
                v-if="!$v.email.maxLength"
              >ایمیل کاربر نمیتواند بیشتر از {{$v.email.$params.maxLength.max}} کاراکتر داشته باشد</p>

              <input
                type="password"
                placeholder="Password"
                v-model="password"
                @blur="$v.password.$touch()"
                :class="{invalid:$v.password.$error}"
              >
              <p
                class="text-danger"
                v-if="!$v.password.required && $v.password.$dirty"
              >لطفا کلمه عبور را وارد کنید</p>

              <p
                class="text-danger"
                v-if="!$v.password.minLength"
              >کلمه عبور باید حداقل شمال {{$v.password.$params.minLength.min}} کاراکتر باشد</p>

              <input
                type="password"
                placeholder="RePassword"
                v-model="rePassword"
                @input="$v.rePassword.$touch()"
                :class="{invalid:$v.rePassword.$error}"
              >

              <p
                class="text-danger"
                v-if="!$v.rePassword.sameAs && $v.rePassword.$dirty"
              >کلمه عبور مغایرت دارد</p>

              <textarea id="Address" rows="5" placeholder="Address" v-model="address"></textarea>
              <br>
              <br>
              <a
                @click.prevent="RegisterUser()"
                class="btn btn-block submit-btn"
                :disabled="$v.$invalid"
              >Sign Up</a>
            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import {
  required,
  maxLength,
  email,
  minLength,
  sameAs
} from "vuelidate/lib/validators";
export default {
  data() {
    return {
      name: "",
      family: "",
      email: "",
      password: "",
      rePassword: "",
      address: ""
    };
  },
  methods: {
    RegisterUser() {
      const register = {
        name: this.name,
        family: this.family,
        email: this.email,
        password: this.password,
        address: this.address
      };
      this.$store.dispatch("RegisterUser", register);
    }
  },
  validations: {
    email: {
      required,
      email,
      maxLength: maxLength(100),
      unique: function(val) {
        if (val === "") return true;

        return this.$http
          .get("Account/IsExistUserByEmail", {
            params: { email: val }
          })
          .then(
            response => {
              console.log(response);
              return !response.body.isExist;
            },
            error => {
              console.log(error);
            }
          );
      }
    },
    password: {
      minLength: minLength(6),
      required
    },
    rePassword: {
      sameAs: sameAs("password")
    }
  }
};
</script>

<style>
.invalid {
  border: 1px solid red !important;
  box-shadow: 0 0 5px red !important;
  background-color: lightpink !important;
}
</style>
