<template>
  <div class="form">
    <q-form @submit.prevent="createPost">
      <div>
        <label for="username">username</label>
        <q-input type="text" id="username" v-model="formData.username" lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"/>
      </div>
      <div>
        <label for="password">Password</label>
        <q-input type="text" id="password" v-model="formData.password" lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"/>
      </div>
    <button>Submit</button>
    </q-form>
    <div>
      <h7 class="jwt">{{!this.value ? null : 'JWT: '}}</h7>
      <h7>{{!this.value ? null : [this.value.data.data.jwt, this.value.data.data.userData]}}</h7>
    </div>
      <div>
        <h7 class="userData">{{!this.value ? null : 'User Data: '}}</h7>
        <h7>{{!this.value ? null : this.value.data.data.userData}}</h7>
      </div>
  </div>
</template>

  <script>
  import axios from 'axios'
    export default {
      name: 'CreatePost',
      data() {
        return {
          value: null,
          formData :{
            username: '',
            password: '',
            },
        }
    },
    methods: {
      createPost() {
        axios.post('https://demo.inleague.io/api/public/authenticate', this.formData)
        .then(response => (this.value = response))
        .catch(error => (error.code === "ERR_BAD_REQUEST" || error.request.status === 500 ? alert(`bad request: ${error.code} ${error.request.status}`) : alert('Failed to connect')))
        }
      }
    }
  </script>

  <style scoped>

  </style>
