<template>
  <div class="hello">
    <h2>Essential Links</h2>
    <form>
      <span>用户名：</span><input type='text' v-model="username"></input><br>
      <span>密码：    </span><input type='text' v-model="password"></input><br>
      <input type='button' value="登录" @click="sub()"></input>
    </form>
  </div>
</template>
<script>
  //import axios from 'axios'
    export default {
        data() {
            return {
                username: '',
                password: '',
            }
        },
        create() {
            console.log("初始化触发")
        },
        methods: {
            sub() {
               this.$axios.get('http://192.168.0.113/login?username='+this.username+'&password='+this.password)
                    .then(function (response) {
                        alert(JSON.stringify(response.data))
                    })
            }
        }
    }
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1, h2 {
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
