<template>
  <form v-on:submit.prevent="submitEvent">
    <div>
      <label for="username">id: </label>
      <input type="text" name="username" id="username" v-model="username">
    </div>
    <div>
      <label for="pw">pw: </label>
      <input type="password" name="pw" id="pw" v-model="password">
    </div>
    <button type="submit">login</button>
  </form>
</template>

<script>
import axios from 'axios';

export default {
  data : function(){
    return {
      username : '',
      password : ''
      }
  },
  methods : {
    submitEvent : function(){
      //event.prevendDefault();
      console.log(this.username, this.password);
      var url = 'https://jsonplaceholder.typicode.com/users';
      var data = {
        username: this.username,
        password: this.password
      }
      axios.post(url, data)
        .then(function(response) {
          console.log(response);
        })
        .catch(function(error) {
          console.log(error);
        });
    }
  }
}
</script>

<style>

</style>