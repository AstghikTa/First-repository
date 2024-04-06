<script>
export default{
    data(){
        return{
  value: 0,   
  rate: 400,
  mode: 'AMD'       
        };
    },
methods: {
    handleInput(event){
        this.value = event.target.value;
    },
handleInputFocus(){
    if(+this.value === 0){
        this.value = '';
    }
},
toggleMode(){
    if(this.mode === 'AMD'){
        this.mode = 'USD';
    }else{
        this.mode = 'AMD';
    }
    this.value = 0;
}
}

}

</script>


<template>
    <div v-if="mode==='AMD'"> 
<h4 class="text"> AMD -> USD </h4>
<input class="inputBtn" type="number" 
:value="value"  
@click="handleInput" 
@focus="handleInputFocus">
<input class="inputBtn" type="number" readonly :value="value/rate">

<button class="toggle" @click="toggleMode">USD -> AMD </button>
</div>

<div v-else>
<h4 class="text"> USD -> AMD </h4>
<input class="inputBtn" type="number" 
:value="value"  
@click="handleInput" 
@focus="handleInputFocus">
<input class="inputBtn" type="number" readonly :value="value*rate">

<button class="toggle" @click="toggleMode">AMD -> USD </button>
</div>

</template>


<style>
.text{
    margin-left: 117px;
   color: crimson;
font-size: x-large;
}
.inputBtn{
    align-items: center;
    margin: 15px;
    height: 30px;
}
.toggle{
background-color: rgb(110, 185, 110);
/* margin-left: 300px; */
/* margin-top: auto;
margin-right: 500px; */

}
</style>