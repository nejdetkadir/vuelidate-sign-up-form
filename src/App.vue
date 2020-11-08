<template>
  <div class="container mt-5">
    <div class="row">
      <div class="col-md-8 mx-auto">
        <div class="card shadow-lg p-3 mb-5 bg-white rounded" style="width: 100%;">
          <div class="card-body">
            <div class="text-center mb-5">
              <img src="../src/assets/logo.svg" alt="">
            </div>
            <form>
              <div class="form-group">
                <label for="name">Your name and surname</label>
                <input type="text" class="form-control" id="name">
                <small style="display: none" class="form-text text-danger"></small>
              </div>
              <div class="form-group">
                <label for="email">Your email</label>
                <input type="email" class="form-control" id="email">
                <small style="display: none" class="form-text text-danger"></small>
              </div>
              <div class="form-group">
                <label for="phone">Your phone number</label>
                <input type="text" class="form-control" id="phone">
                <small style="display: none" class="form-text text-danger"></small>
              </div>
              <div class="form-group">
                <label for="bio">About yourself</label>
                <textarea class="form-control" id="bio" rows="3"></textarea>
                <small style="display: none" class="form-text text-danger"></small>
              </div>
              <div class="form-group">
                <label for="pass">Password</label>
                <input type="password" class="form-control" id="pass">
                <small style="display: none" class="form-text text-danger"></small>
              </div>
              <div class="form-group">
                <label for="repass">Password again</label>
                <input type="password" class="form-control" id="repass">
                <small style="display: none" class="form-text text-danger"></small>
              </div>
              <button type="submit" class="btn btn-success btn-block">SIGN UP</button>
            </form>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'App',
  }
</script>

<style>

</style>
