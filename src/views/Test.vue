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
    axios
      .get("//numbersapi.com/42")
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