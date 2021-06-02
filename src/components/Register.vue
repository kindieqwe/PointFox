<template>
  <div id="mainWrapper">
    <div id="mainContent">
      <el-card class="box-card">
        <div slot="header" class="clearfix">
          <span>用户注册</span>
        </div>
        <div id="registerContent">
          <el-input id="username" v-model="newUser.newusername" clearable></el-input>
          <el-input
            id="password"
            v-model="newUser.newpassword"
            clearable
            show-password
          ></el-input>
        </div>
        <div id="submitContent">
          <el-button id="systemSubmit" @click="registerSystem">注册</el-button>
        </div>
      </el-card>
    </div>
  </div>
</template>

<script>
import Axios from 'axios'
const url = 'http://localhost:3000'
export default {
  name:"register",
  data(){
    return {
            newUser:{
                newusername:"",
                newpassword:""
            },
            fullscreenLoading: false
        }

  },
  methods:{
    registerSystem(){

      Axios.get(url+'/register',{
        params:this.newUser
      }).then(function
      (resx){

      })
    }
  },
  data() {
    return {
      newUser: {
        username: "",
        password: "",
      },
    };
  },
};
</script>

<style>
#mainWrapper {
  padding-top: 120px;
}
#mainContent {
  width: 400px;
  margin: 0 auto;
}
#systemSubmit {
  background-color: #0a9588 !important;
  border-color: #0a9588 !important;
  color: white !important;
  display: block;
  margin: 0 auto;
}
#password {
  margin: 5px 0px;
}
</style>