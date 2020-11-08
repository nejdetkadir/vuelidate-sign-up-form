<template>
  <div class="container mt-5">
    <div class="row">
      <div class="col-md-8 mx-auto">
        <div class="card shadow-lg p-3 mb-5 bg-white rounded" style="width: 100%;">
          <div class="card-body">
            <div class="text-center mb-5">
              <img src="../src/assets/logo.svg">
            </div>
            <Form></Form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Form from "@/components/Form";

  export default {
    name: 'App',
    components: {
      Form
    }
  }
</script>

<style>
</style>
