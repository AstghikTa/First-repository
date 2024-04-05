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
    console.log(email);
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
   
<button @click="openEmailPrompt()">input your email</button>
<button @click="reset">Reset</button>
<div v-if="email">
  <h1 class="green" v-if="isEmailValid">{{ email }}</h1>
<h1 class="red" v-else>{{ email }}</h1>
</div>

<h4 v-if="email">{{ `The email is ${isEmailValid ? 'valid': 'invalid'}` }}</h4>

  </main>
</template>

<style scoped>
.red{
  border: 1px solid red;
}

.green{
  border: 1px solid green;


}
</style>
