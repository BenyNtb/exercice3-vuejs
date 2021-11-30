<template>
  <div class="wrapper">
    <form id="app" @submit="checkForm">
      <div class="h5 font-weight-bold text-center mb-3">Registration</div>
      <div class="form-group d-flex align-items-center">
        <div class="icon"><span class="far fa-user"></span></div> <input autocomplete="off" type="text"
          class="form-control" placeholder="First Name" id="firstname" v-model="form.firstname"
          >
        <p v-if="form.errors.length >= 1">
    <b>Please correct the following error(s):</b>
    <ul>
      <li v-for="error in form.errors" v-bind:key="error">{{ error }}</li>
    </ul>
  </p>
      </div>
      <div class="form-group d-flex align-items-center">
        <div class="icon"><span class="far fa-user"></span></div> <input autocomplete="off" type="text"
          class="form-control" placeholder="Last Name" id="lastname" v-model="form.lastname"
        >
        
      </div>
      <div class="form-group d-flex align-items-center">
        <div class="icon"><span class="far fa-envelope"></span></div> <input autocomplete="off" type="email"
          class="form-control" 
          placeholder="Email" id="email" v-model="form.email">
        <!-- <p v-if="errors.length">
    <b>Please correct the following error(s):</b>
    <ul>
      <li v-for="error in errors"> {{ error }}</li>
    </ul>
  </p> -->
      </div>

      <div class="form-group d-flex align-items-center">
        <div class="icon"><span class="fas fa-key"></span></div> <input autocomplete="off" type="password"
          class="form-control"
          placeholder="Password" id="password" v-model="form.password">
        <div class="icon btn"><span class="fas fa-eye-slash"></span></div>
        <!-- <p v-if="errors.length">
    <b>Please correct the following error(s):</b>
    <ul>
      <li v-for="error in errors" >{{ error }}</li>
    </ul>
  </p> -->
      </div>

      <div class="btn btn-primary mb-3">Signup</div>
      
    </form>
  </div>
</template>

<script>
  export default {
    name: 'App',
  data(){
    return {
      form:{
        errors:[],
        firstname:null,
        lastname:null,
        email:null,
        password:null,
      },
    
    }
  },
  methods:{
    checkForm:function(e) {
      if(this.form.firstname && this.form.lastname) return true;
      this.form.errors = [];
      if(!this.form.firstname) this.form.errors.push("First name required.");
      if(!this.form.lastname) this.form.errors.push("Last name required.");
      e.preventDefault();
    }
  }
  } 
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800;900&display=swap');

  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif
  }

  body {
    min-height: 100vh;
    background: linear-gradient(to bottom, #F27777, #F27777)
    
  }

  .wrapper {
    max-width: 450px;
    margin: 50px auto;
    padding: 20px 30px;
    min-height: 300px;
    background-color: #ffffff27;
    border-top: 1px solid #ffffff6e;
    border-left: 1px solid #ffffff6e;
    border-radius: 15px
  }

  .wrapper .h5 {
    color: #ddd
  }

  .wrapper .form-group {
    border-bottom: 1px solid #ccc;
    margin-bottom: 1.5rem
  }

  .wrapper .form-group:hover {
    border-bottom: 1px solid #eee
  }

  .wrapper .form-group .icon {
    color: #e8e8e8
  }

  .wrapper .form-group .form-control {
    background: inherit;
    border: none;
    border-radius: 0px;
    box-shadow: none;
    color: #e9e9e9
  }

  .wrapper .form-group input::placeholder {
    color: #ccc
  }

  .wrapper .form-group input:focus::placeholder {
    opacity: 0
  }

  .wrapper .form-group .fa-phone {
    transform: rotate(90deg)
  }

  .wrapper .option {
    color: #ccc;
    display: block;
    position: relative;
    padding-left: 25px;
    margin-bottom: 12px;
    cursor: pointer;
    user-select: none
  }

  .wrapper .option:hover {
    color: #eee
  }

  .wrapper .option input {
    position: absolute;
    opacity: 0;
    cursor: pointer;
    height: 0;
    width: 0
  }

  .wrapper .checkmark {
    position: absolute;
    top: 3px;
    left: 0;
    height: 18px;
    width: 18px;
    background-color: inherit;
    border: 2px solid #ccc;
    border-radius: 2px
  }

  .wrapper .option input:checked~.checkmark {
    transition: 300ms ease-in-out all
  }

  .wrapper .checkmark:after {
    content: "\2713";
    position: absolute;
    display: none;
    font-weight: 600;
    color: #FFF;
    font-size: 0.9rem
  }

  .wrapper .option input:checked~.checkmark:after {
    display: block
  }

  .wrapper .option .checkmark:after {
    left: 2px;
    top: -4px;
    width: 5px;
    height: 10px
  }

  .wrapper .btn.btn-primary {
    position: relative;
    color: #eee;
    padding: 0.3rem 1rem;
    border-radius: 20px;
    border: 1px solid #ddd;
    background-color: inherit;
    box-shadow: none;
    overflow: hidden
  }

  .wrapper .btn.btn-primary:hover {
    background-color: #b4b4b433;
    color: #fff
  }

  .wrapper .terms {
    color: #bbb;
    font-size: 0.85rem;
    text-align: center
  }

  .wrapper .terms a {
    text-decoration: none;
    color: #eee
  }

  .wrapper .terms a:hover {
    color: #fff
  }

  .wrapper .connect {
    position: relative
  }

  .wrapper .connect::after {
    content: "or";
    position: absolute;
    top: -12px;
    width: 80px;
    left: 39%;
    text-align: center;
    color: #eee;
    z-index: 100;
    background-color: rgba(255, 255, 255, 0.315);
    background-color: #1f5588
  }

  .wrapper .social-links {
    margin-top: 50px;
    position: relative;
    list-style: none;
    display: flex;
    justify-content: space-around
  }

  .wrapper .social-links li a {
    font-size: 1.2rem;
    width: 50px;
    height: 50px;
    background-color: #ffffff17;
    border: 1px solid #ffffff66;
    border-right: 1px solid #ffffff33;
    border-bottom: 1px solid #ffffff33;
    display: flex;
    text-decoration: none;
    justify-content: center;
    align-items: center;
    color: #fff;
    border-radius: 6px;
    box-shadow: 0 5px 30px #004683e0;
    transition: 0.5s;
    overflow: hidden
  }

  .wrapper .social-links li a:hover {
    transform: translateY(-20px)
  }

  .wrapper .social-links li a::before,
  .wrapper .btn.btn-primary::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 25px;
    height: 100%;
    background-color: rgba(255, 255, 255, 0.6);
    transform: skew(45deg) translateX(130px);
    transition: .5s;
    opacity: 0
  }

  .wrapper .social-links li a:hover:before,
  .wrapper .btn.btn-primary:hover::before {
    opacity: 1;
    transform: skew(45deg) translateX(-130px)
  }

  @media(max-width: 460px) {
    .wrapper {
      margin: 15px;
      padding: 20px
    }

    .wrapper .connect::after {
      left: 38%
    }
  }

  @media(max-width: 345px) {
    .wrapper .connect::after {
      left: 32%
    }
  }
</style>