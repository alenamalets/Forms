<template>
  <div class="container">
    <form>
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <!-- Exercise 1 -->
          <!-- Create a Signup Form where you retrieve the following Information -->
          <!-- Full Name (First Name + Last Name) -->
          <!-- Mail -->
          <!-- Password -->
          <!-- Store Data? Yes/No -->
          <div v-if="!submitted">
              <name v-model="fullname"></name>
            <!-- <div class="form-group">
              <label for="first-name">First Name</label>
              <input type="text" id="first-name" class="form-control" v-model="name.firstname" />
            </div>
            <div class="form-group">
              <label for="last-name">Last Name</label>
              <input type="text" id="last-name" class="form-control" v-model="name.lastname" />
            </div> -->
            <div class="form-group">
              <label for="email">Email</label>
              <input type="text" id="email" class="form-control" v-model="email" />
            </div>
            <div class="form-group">
              <label for="password">Password</label>
              <input type="text" id="password" class="form-control" v-model="password" />
            </div>
            <div class="form-group">
              <p>Store Data?</p>
              <label for="yes">
                <input type="radio" id="yes" value="Yes" v-model="data" /> Yes
              </label>
              <label for="no">
                <input type="radio" id="no" value="No" v-model="data" /> No
              </label>
            </div>
             <button @click.prevent="submitForm">Submit</button>

          </div>
          <!-- Exercise 2 -->
          <!-- Only display the Form if it has NOT been submitted -->
          <!-- Display the Data Summary ONCE the Form HAS been submitted -->

         
          <!-- Exercise 3 -->
          <!-- Edit the Example from above and create a custom "Full Name" Control -->
          <!-- which still holds the First Name and Last Name Input Field -->
        </div>
      </div>
    </form>
    <hr />
    <div class="row" v-if="submitted">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4>Your Data</h4>
          </div>
          <div class="panel-body">
            <p>Full Name: {{fullname}}</p>
            <p>Mail: {{ email }}</p>
            <p>Password: {{ password }}</p>
            <p>Store in Database?: {{ data }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import Name from './Name.vue'

export default {
  data() {
    return {
      fullname: '',
      email: "",
      password: "",
      data: "Yes",
      submitted: false
    };
  },
  methods: {
    submitForm() {
      this.submitted = true;
    }
  },
  components: {
      name: Name,
  }
};
</script>

<style>
</style>
