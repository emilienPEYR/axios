<template>
  <div id="app">
    <h1>infos du compte</h1>
    <div v-for="info in info" :key="info" class="currency">
      {{ info.login }} <br>
      {{ info.id }} <br>
      {{ info.avatar_url }}
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "HelloWorld",
  data() {
    return {
      info: null,
    };
  },
  mounted() {
    axios
      .get("https://api.github.com/users/emilienPEYR")
      .then((response) => (this.info = response));
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
