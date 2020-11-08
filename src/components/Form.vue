<template>
  <form @submit.prevent="onsubmit()">
    <div class="form-group">
      <label for="name">Your name and surname</label>
      <input v-model="$v.userName.$model" type="text" class="form-control" id="name" :class="{'is-invalid' : $v.userName.$error, 'is-valid': !$v.userName.$invalid}">
      <small v-if="!$v.userName.required" class="form-text text-danger">This value is required.</small>
      <small v-if="!$v.userName.minLength" class="form-text text-danger">This value must be bigger than {{$v.userName.$params.minLength.min}} characters.</small>
      <small v-if="!$v.userName.maxLength" class="form-text text-danger">This value must be smaller than {{$v.userName.$params.maxLength.max}} characters.</small>
    </div>
    <div class="form-group">
      <label for="email">Your email</label>
      <input v-model="$v.userEmail.$model" type="email" class="form-control" id="email" :class="{'is-invalid' : $v.userEmail.$error, 'is-valid': !$v.userEmail.$invalid}">
      <small v-if="!$v.userEmail.required" class="form-text text-danger">This value is required.</small>
      <small v-if="!$v.userEmail.maxLength" class="form-text text-danger">This value must be smaller than {{$v.userEmail.$params.maxLength.max}} characters.</small>
      <small style="display: none" class="form-text text-danger"></small>
    </div>
    <div class="form-group">
      <label for="phone">Your phone number</label>
      <input v-model="$v.userPhone.$model" type="text" class="form-control" placeholder="ex: 5313235151" id="phone" :class="{'is-invalid' : $v.userPhone.$error, 'is-valid': !$v.userPhone.$invalid}">
      <small v-if="!$v.userPhone.required" class="form-text text-danger">This value is required.</small>
      <small v-if="!$v.userPhone.numeric" class="form-text text-danger">This value must be numeric.</small>
      <small v-if="!$v.userPhone.maxLength || !$v.userPhone.minLength" class="form-text text-danger">This value must be {{$v.userPhone.$params.maxLength.max}} characters.</small>
    </div>
    <div class="form-group">
      <label for="pass">Password <small>(just numeric)</small></label>
      <input v-model="$v.userPassword.$model" type="password" class="form-control" id="pass" :class="{'is-invalid' : $v.userPassword.$error, 'is-valid': !$v.userPassword.$invalid}">
      <small v-if="!$v.userPassword.required" class="form-text text-danger">This value is required.</small>
      <small v-if="!$v.userPassword.numeric" class="form-text text-danger">This value must be numeric.</small>
      <small v-if="!$v.userPassword.minLength" class="form-text text-danger">This value must be bigger than {{$v.userPassword.$params.minLength.min}} characters.</small>
      <small v-if="!$v.userPassword.maxLength" class="form-text text-danger">This value must be smaller than {{$v.userPassword.$params.maxLength.max}} characters.</small>
    </div>
    <div class="form-group">
      <label for="repass">Password again</label>
      <input v-model="$v.userRePassword.$model" type="password" class="form-control" id="repass" :class="{'is-invalid' : $v.userRePassword.$error, 'is-valid': !$v.userRePassword.$invalid}">
      <small v-if="!$v.userRePassword.required" class="form-text text-danger">This value is required.</small>
      <small v-if="!$v.userRePassword.sameAs" class="form-text text-danger">This password must equal to first password</small>
      <small v-if="!$v.userRePassword.numeric" class="form-text text-danger">This value must be numeric.</small>
      <small v-if="!$v.userRePassword.minLength" class="form-text text-danger">This value must be bigger than {{$v.userRePassword.$params.minLength.min}} characters.</small>
      <small v-if="!$v.userRePassword.maxLength" class="form-text text-danger">This value must be smaller than {{$v.userRePassword.$params.maxLength.max}} characters.</small>
    </div>
    <button type="submit" :disabled="$v.$invalid" class="btn cd btn-success btn-block">SIGN UP</button>
  </form>
</template>

<script>
  import {required, minLength, maxLength, email, numeric, sameAs} from "vuelidate/lib/validators";
  import swal from 'sweetalert';
  export default {
    name: "Form",
    data() {
      return{
        userName: null,
        userEmail: null,
        userPhone: null,
        userPassword: null,
        userRePassword: null
      }
    },
    methods: {
      onsubmit() {
        swal("Good job!", "You submitted the form!", "success");
      }
    },
    validations: {
      userName: {
        required,
        minLength: minLength(3),
        maxLength: maxLength(60)
      },
      userEmail: {
        required,
        email,
        maxLength: maxLength(50)
      },
      userPhone: {
        required,
        numeric,
        maxLength: maxLength(10),
        minLength: minLength(10)
      },
      userPassword: {
        required,
        numeric,
        minLength: minLength(8),
        maxLength: maxLength(16)
      },
      userRePassword: {
        required,
        numeric,
        minLength: minLength(8),
        maxLength: maxLength(16),
        sameAs: sameAs('userPassword')
      }
    }
  }
</script>

<style scoped>

</style>
