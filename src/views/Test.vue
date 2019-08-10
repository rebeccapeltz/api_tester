<template>
  <div class="test">
     {{results}}
  </div>

</template>

<script>
import axios from "axios";
export default {
  name: "Test",
  data () {
    return {
      results: null,
      errors: [],
    };
  },
  created: function () {
    let proxyUrl = 'https://cors-anywhere.herokuapp.com/'
    let targetUrl = 'http://numbersapi.com/42'
    axios
      .get(proxyUrl + targetUrl)
      .then(response => {
        this.results = response.data;
      })
      .catch(error => {
        this.errors.push(error);
      });
  }



};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>