<template>
  <div class="log">
    <div class="register">
      <p class="account">
        <input type="text" placeholder="请输入账号" v-model="account" @change=""/>
        <span v-show="accountHint">*请输入由中文数字组合的名称</span>
      </p>
      <p class="password">
        <input type="password" placeholder="请输入密码" v-model="password" />
        <span v-show="passwordHint">*请输入至少六位由英文、数字组合的密码</span>
      </p> 
      <p>
        <input type="password" placeholder="请确认密码" v-model="repeatpwd" />
        <span v-show="repeatpwdHint">*密码不一致</span>
      </p>  
      <div>
        <button @click="ChenckRegister">注册</button>
      </div>   
    </div>
    <div class="logIn">
      <p class="account">
        <input type="text" placeholder="请输入账号" />
        <span>*请输入正确的账号</span>
      </p>
      <p class="password">
        <input type="password" placeholder="请输入密码" />
        <span>*密码不匹配</span>
      </p> 
      <div>
        <button>登录</button>
      </div>        
    </div>    
  </div>
</template>

<script>
export default {
  data () {
    return {
      account: '',
      password : '',
      repeatpwd : '',
      accountHint: false,
      passwordHint: false,
      repeatpwdHint: false
    }
  },
  methods: {
    accountBlur () {
      console.log(1)
    },
    ChenckRegister () {
      let accountMatch = /^([\u4E00-\uFA29]|[\uE7C7-\uE7F3]|[a-zA-Z0-9_]){1,20}$/; 
      let passowrdMatch = /[a-zA-Z]?[\d]?/;
      
      if (!accountMatch.test(this.account)) {
        return this.accountHint = true;
      }

      if (!passowrdMatch.test(this.password)) {
        return this.passwordHint = true;
      }

      if (!passowrdMatch.test(this.repeatpwd)) {
        return this.passwordHint = true;
      }
      
    },
    CheckLogIn () {

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .log{
    border: 1px solid #0ff;
  }
  .log p{ 
    overflow: hidden;
  }
  .log input{ 
    float: left; 
    margin-left: 30%;
  }
  .log span{ 
    color:red; 
    font-size: 12px; 
    float:left; 
    margin-left: 5%; 
  }
</style>