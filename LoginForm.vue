<template>
  <div className="auth body">
    <div className="auth body-1">

      <div className="auth body-2">
        <p className="auth email">Username or email address</p>
        <input type="email" v-model="userEmail" placeholder="">
        <p className="auth pass">Password</p>
        <input type="password" v-model="userPass" placeholder="">
      </div>
      <button type="submit" @click="sendData()">Отправить</button>
    </div>
  </div>


</template>


<script>

export default {

  data() {
    return {
      users:[],
      error: '',
      userEmail: '',
      userPass: '',
      // userEmail: '',
    }
  },

  methods: {
    goToLogin(){
      this.$router.push('/loginForm')
    },

    sendData(){
      // if(!this.userEmail.includes('@') || !this.userEmail.includes('.')){
      //   this.error = 'нет спец символа в Email';
      //   return;
      // }
      if(!this.userPass.includes('!','$','@')){
        this.error = 'нет Симола';
        return;
      }


      this.error = '';
      this.users.push({
        name: this.userName,
        email: this.userEmail,
        pass: this.userPass,
      })
    }
  }
}


</script>


<style>
.auth.body{
  height: 217.33px;
  //line-height: 21px;
  width: 288px;
  margin: 0 auto;
  //margin-top: 16px;
  border: 0.667px solid #000000;
  //padding: 16px;
  padding-bottom: 16px;

  font-size: 14px;
  font-family: "Segoe UI";
  font-weight: 600;

  border-radius: 0.375rem;
  background: rgb(255, 255, 255);
}
.auth.body-1{
  height: 184px;  /*Высота*/
  //line-height: 21px;
  width: 254.67px; /*Ширина*/
  //margin: 14px;
  padding: 16px;
  //background: red;
}
.auth.body-2{
  margin-bottom: 1px;
  //background: limegreen;
}
.auth.email{

  height: 21px;  /*Высота*/
  //line-height: 21px;
  width: 254.67px; /*Ширина*/
  margin-top: 0px;
  margin-bottom: 8px;

  //background: aqua;
}
.auth.pass{
  height: 21px;  /*Высота*/
  width: 254.67px; /*Ширина*/
  margin-top: 4px;
  margin-bottom: 8px;
  //background: aqua;
}

input{
  height: 31.33px;
  width: 244.67px;
  margin-top: 4px;
  padding-left: 10px;
  margin-bottom: 16px;
  border: 0.667px solid #333333;
  border-radius: 5px;
  font-size: 14px;
  text-align: start;

  //background: darkgrey;
}
button{
  height: 31.33px;
  width: 260.67px;
  border: 1px;
  border-radius: 8px;
  background-color: #2E9A40;
}

</style>
