<template>
  <div class="hello">
    axios_GET:
    <!-- <input /> -->
    <button @click="send">GET</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "Welcome to Your Vue.js App"
    };
  },
  methods: {
    send() {
      let that = this;
      that.$axios
        .get("http://192.168.13.236:5005/v1/getdiagdesc/肘关节疼痛", {
          params: {
            // ID: 12345
          },
          withCredentials: true, // default
          headers:{'content-type': 'application/json' },
          responseType: 'json'
        })
        .then(function(response) {
          console.log(response);
        })
        .catch(function(error) {
          console.log(error);
        });
      // that.$axios({
      //     method: "get",
      //     url: "http://localhost:3000/",
      //     withCredentials: false, // default
      //   })
      //   .then(function(response) {
      //     console.log(response);
      //   });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
