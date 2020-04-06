<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <!--Bootstrap按钮控件--->
    <div class='btn btn-primary'>{{msg}}</div>  
    <p> awesome !</p>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  //name: 'HelloWorld',
  //props: {
  //  msg: String
  //}
  data() {
    return {
      msg: ''
    };
  },
  methods: {
    getMessage() {
      const path = 'http://localhost:5000/';
      axios
        .get(path)
        .then(res => {
          this.msg = res.data;
        })
        .catch(error => {
          console.error(error);
        });
    }
  },
  created() {
    this.getMessage();
  }
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
h1 {
  margin-top: 60px;
}
</style>
