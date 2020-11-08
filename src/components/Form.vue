<template>
  <form @submit.prevent="onsubmit()">
    <div class="form-group">
      <label for="name">Your name and surname</label>
      <input v-model="form.userName" type="text" class="form-control" id="name">
      <small style="display: none" class="form-text text-danger"></small>
    </div>
    <div class="form-group">
      <label for="email">Your email</label>
      <input v-model="form.userEmail" type="email" class="form-control" id="email">
      <small style="display: none" class="form-text text-danger"></small>
    </div>
    <div class="form-group">
      <label for="phone">Your phone number</label>
      <input v-model="form.userPhone" type="text" class="form-control" id="phone">
      <small style="display: none" class="form-text text-danger"></small>
    </div>
    <div class="form-group">
      <label for="bio">About yourself</label>
      <textarea v-model="form.userBio" class="form-control" id="bio" rows="3"></textarea>
      <small style="display: none" class="form-text text-danger"></small>
    </div>
    <div class="form-group">
      <label for="pass">Password</label>
      <input v-model="form.userPassword" type="password" class="form-control" id="pass">
      <small style="display: none" class="form-text text-danger"></small>
    </div>
    <div class="form-group">
      <label for="repass">Password again</label>
      <input v-model="form.userRePassword" type="password" class="form-control" id="repass">
      <small style="display: none" class="form-text text-danger"></small>
    </div>
    <button type="submit" class="btn btn-success btn-block">SIGN UP</button>
  </form>
</template>

<script>
  export default {
    name: "Form",
    data() {
      return{
        form: {
          userName: null,
          userEmail: null,
          userPhone: null,
          userBio: null,
          userPassword: null,
          userRePassword: null
        }
      }
    },
    methods: {
      onsubmit() {
        alert('submitted!');
      }
    }
  }
</script>

<style scoped>

</style>
