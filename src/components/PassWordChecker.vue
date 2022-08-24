<template >
<div class="main">
    <div class="checker">
         Hello
    <div class="input">
        <span style="margin-left: 10px;">Email</span>
        <input class="input-box" type="email" placeholder="Enter your email address" >
    </div>
    <div class="input">
        <span style="margin-left: 10px;">Password</span>
        <div >
            <input @input="check" v-model="password" class="input-box" :type="showPassword ? 'password' : 'text'" placeholder="Enter your password" >
            <span @click="showPassword =!showPassword" ><font-awesome-icon  :icon="showPassword ? 'eye' : 'eye-slash'"></font-awesome-icon>
            </span>
        </div>
    </div>
    <div class="conditions">        
        <span>Lowercase&Uppercase <font-awesome-icon :icon="lowerandupper ? 'check' : 'circle-minus'"> </font-awesome-icon></span>
        <span>Number (0-9) <font-awesome-icon :icon="isnumber ? 'check' : 'circle-minus'"> </font-awesome-icon></span>
        <span>Special Character (!@#$%^&*) <font-awesome-icon :icon="specialchar ? 'check' : 'circle-minus'"> </font-awesome-icon></span>
        <span>Atleast 8 Character <font-awesome-icon :icon="atleast ? 'check' : 'circle-minus'"> </font-awesome-icon></span>
        <button @click="buttonClick" class="button">Create An Account</button>
        <p>Already have an account? Signin <a href="/">here</a></p>
    </div>
    </div>
</div>
    
</template>
<script>
export default{

    data(){
    return{
      showPassword:true,
      password:null,
      lowerandupper:false,
      isnumber:false,
      specialchar:false,
      atleast:false
    }   
  },
  methods:{
    buttonClick(){
        console.log("Have a good day :)")
    },
    check(){
        let data = this.password
        data.length>7 ? this.atleast=true : this.atleast=false;
        data.match(/\d+/g) ? this.isnumber = true : this.isnumber = false;
        data.match(/([a-z].*[A-Z])|([A-Z].*[a-z])/) ? this.lowerandupper = true : this.lowerandupper = false;
        let spChars = /[!@#$%^&*()_+\-=\[\]{};':"\\|,.<>\/?]+/;
        if(spChars.test(data)){
        this.specialchar= true;
        } else {
        this.specialchar= false;
        }
    },
  }
}
</script >
<style>
.checker{
    font-family: Arial, Helvetica, sans-serif;
    font-size: 30px;
    padding-top: 40px;
    height: 500px;
    width: 300px;
    background-color: aliceblue;
    border-radius: 25px;
}
.input{
    caret-color: red;
    font-weight: 600;
    margin: 15px;
    font-size: 15px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    
}
.button{
    cursor: pointer;
    display: flex;
    margin:30px 15px 15px 15px;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: darkcyan;
    color:white;
    width: 200px;
    height: 40px;
    text-shadow: 1px 1px black;
    border-radius: 18px;
}
.conditions{
    font-weight: 100;
    margin:15px 15px 15px 30px;
    font-size: 15px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    
}
.input-box{
    margin: 10px;
    border-radius: 5px;
    border-style: solid;
    border-width: 1px;
    width: 200px;
    height: 25px;
}
.main{
    font-size: 15px;
}
</style>