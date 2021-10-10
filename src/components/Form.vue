<template>
  <div class="forms-container">
    <div class="signin-signup">
      <form
        action="#"
        class="sign-in-form"
        name="form"
        v-on:submit.prevent="login()"
      >
        <h2 class="title">Sign in</h2>
        <div class="input-field">
          <i class="fas fa-user"></i>

          <input :name='email' type="text" placeholder="Email" />
        </div>
        <div id="email_error">Please fill up your Email !!</div>
        <div class="input-field">
          <i class="fas fa-lock"></i>
          <input id="sandi" :name='pw' :type='sandi' placeholder="Password" />
          <span class="eye" @click="eyePassword()">
            <i id="hide1" class="fas fa-eye"></i>
            <i id="hide2" class="fas fa-eye-slash"></i>
          </span>
        </div>
        <div id="pass_error">Password minimal 6 characters ^_^</div>
        <button type="submit" class="btn solid">LOGIN</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "Form",
  data: ()=>{
    return{
      sandi: 'password',
      hide1: 'none',
      hide2: 'block'
    }
  },
  methods:{
    eyePassword() {

      if (this.sandi === "password") {
        this.sandi = "text";
        this.hide1 = "block";
        this.hide2 = "none";
      } else {
        this.sandi = "password";
        this.hide1 = "none";
        this.hide2 = "block";
      }
    },

    // login() {
    //   var email = document.forms["form"]["email"];
    //   var password = document.forms["form"]["pw"];

    //   var email_error = document.getElementById("email_error");
    //   var pass_error = document.getElementById("pass_error");

    //   email.addEventListener("textInput", verifyEmail);
    //   password.addEventListener("textInput", verifyPassword);
    //   if (email.value.length < 9) {
    //     email.style.border = "1px solid red";
    //     email.style.borderRadius = "55px";
    //     email.style.width = "380px";
    //     email.style.padding = "0 4rem";
    //     email.style.position = "relative";
    //     email.style.right = "60px";
    //     email_error.style.display = "block";
    //     email.focus();
    //     return false;
    //   }
    //   if (password.value.length < 6) {
    //     password.style.border = "1px solid red";
    //     password.style.borderRadius = "55px";
    //     password.style.width = "380px";
    //     password.style.padding = "0 4rem";
    //     password.style.position = "relative";
    //     password.style.right = "60px";
    //     pass_error.style.display = "block";
    //     password.focus();
    //     return false;
    //   }
    // },

    // verifyEmail() {
    //   if (email.value.length >= 9) {
    //     email.style.border = "1px solid silver";
    //     email.style.borderRadius = "55px";
    //     email.style.width = "380px";
    //     email.style.padding = "0 4rem";
    //     email.style.position = "relative";
    //     email.style.right = "60px";
    //     email_error.style.display = "none";
    //     return true;
    //   }
    // },

    // verifyPassword() {
    //   if (password.value.length > 4) {
    //     password.style.border = "1px solid silver";
    //     password.style.borderRadius = "55px";
    //     password.style.width = "380px";
    //     password.style.padding = "0 4rem";
    //     password.style.position = "relative";
    //     password.style.right = "60px";
    //     pass_error.style.display = "none";
    //     return true;
    //   }
    // },
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;600;700;800&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body,
input {
  font-family: "Poppins", sans-serif;
  background: linear-gradient(to right, #ffffff, #7ed6ff);
}
/* .pict {
  position: relative;
  width: 100px;
  height: 100px;
} */

.container {
  position: relative;
  width: 100%;
  /* background-color: #fff; */
  min-height: 100vh;
  overflow: hidden;
}

.signin-signup {
  position: absolute;
  top: 50%;
  transform: translate(-50%, -50%);
  left: 75%;
  width: 50%;
  transition: 1s 0.7s ease-in-out;
  display: grid;
  grid-template-columns: 1fr;
  z-index: 5;
}

form {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  padding: 0rem 5rem;
  transition: all 0.2s 0.7s;
  overflow: hidden;
  grid-column: 1 / 2;
  grid-row: 1 / 2;
}

form.sign-in-form {
  z-index: 2;
}

.title {
  font-size: 2.2rem;
  color: #444;
  margin-bottom: 10px;
}

.input-field {
  max-width: 380px;
  width: 100%;
  background-color: #f0f0f0;
  margin: 10px 0;
  height: 55px;
  border-radius: 55px;
  display: grid;
  grid-template-columns: 15% 85%;
  padding: 0 0.4rem;
  position: relative;
}

.input-field i {
  text-align: center;
  line-height: 55px;
  color: #acacac;
  transition: 0.5s;
  font-size: 1.1rem;
}

.input-field input {
  background: none;
  outline: none;
  border: none;
  line-height: 1;
  font-weight: 600;
  font-size: 1.1rem;
  color: #333;
}

.input-field input::placeholder {
  color: #aaa;
  font-weight: 500;
}

.eye {
  position: absolute;
  left: 330px;
}

#hide1 {
  display: none;
}

.btn {
  width: 150px;
  background-color: #338a41;
  border: none;
  outline: none;
  height: 49px;
  border-radius: 49px;
  color: #fff;
  text-transform: uppercase;
  font-weight: 600;
  margin: 10px 0;
  cursor: pointer;
  transition: 0.5s;
}

.signin-signup #email_error,
.signin-signup #pass_error {
  margin: 0;
  color: red;
  font-size: 10px;
  background: rgba(255, 0, 0, 0.1);
  padding: 5px 8px;
  border-radius: 3px;
  border: 1px solid #ef9a9a;
  display: none;
}

.btn:hover {
  background-color: #51e269;
}

.btn.transparent {
  margin: 0;
  background: none;
  border: 2px solid #fff;
  width: 130px;
  height: 41px;
  font-weight: 600;
  font-size: 0.8rem;
}

@media (max-width: 870px) {
  .container {
    min-height: 800px;
    height: 100vh;
  }
  .signin-signup {
    width: 100%;
    top: 95%;
    transform: translate(-50%, -180%);
    transition: 1s 0.8s ease-in-out;
  }

  .signin-signup,
  .container.sign-up-mode .signin-signup {
    left: 50%;
  }
}
</style>
