<template>
  <div id="app">
    <GoogleLogin :params="params" :renderParams="renderParams" :onSuccess="onSuccess"></GoogleLogin>
  </div>
</template>

<script>
import GoogleLogin from 'vue-google-login';
export default {
  name: 'App',
  data() {
            return {
                // client_id is the only required property but you can add several more params, full list down bellow on the Auth api section
                params: {
                    client_id: "733953378543-779uq6a566lcpf3pe15jgfagjsuq7367.apps.googleusercontent.com"
                },
                // only needed if you want to render the button with the google ui
                renderParams: {
                    width: 250,
                    height: 50,
                    longtitle: true
                }
            }
        },
  components: {
    GoogleLogin
  },
  methods: {
        onSuccess(googleUser) {
            console.log(JSON.stringify(googleUser));
 
            // This only gets the user information: id, name, imageUrl and email
            console.log(JSON.stringify(googleUser.getBasicProfile()));
        }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
