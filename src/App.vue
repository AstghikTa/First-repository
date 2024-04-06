<script >

export default{
data(){
  return{
email: '',
isEmailValid: false,
  };
},

methods: {
  openEmailPrompt(){
    let email = prompt('input your email');
    if(!email){
this.isEmailValid = false;      
return;
    } 
    email = email.trim();
    this.email = email;
   const isValid = this.checkIsEmailValid(email);
   this.isEmailValid = isValid;
  },
 checkIsEmailValid(email){
    const regEmail = /^[\w-.]+@([\w-]+\.)+[\w-]{2,4}$/;
    return regEmail.test(email);
  },
  reset(){
    this.email = '';
    this.isEmailValid = false;
  }
}
}

</script>

<template>
  <main>
   
<button class="emailInputBtn" @click="openEmailPrompt()">Input your email</button>
<button class="restBtn" @click="reset">Reset</button>
<div v-if="email">
  <h1 class="green" v-if="isEmailValid">{{ email }}</h1>
<h1 class="red" v-else>{{ email }}</h1>
</div>

<h4 class="validText" v-if="email">{{ `The email is ${isEmailValid ? 'valid': 'invalid'}` }}</h4>

  </main>
</template>

<style scoped>
.red{
  border: 1px solid red;
  margin-top: 20px;
}

.green{
  border: 1px solid green;
  margin-top: 20px;
}
.validText{
  margin-top: 20px;
}
.emailInputBtn{
  margin: 15px;
  height: 40px;
  width: 300px;
}
.restBtn{
  margin: 15px;
  height: 40px;
  width: 100px;
}
</style>
