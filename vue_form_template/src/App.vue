<template>
  <div id = "frm">
    <h2 id = "heading">{{ title }}</h2>
    <form @submit.prevent = "submitHandler">
      <input placeholder = "Email" class = "inp1" type = "email" v-model = "email" required/>
      <input placeholder = "Password" class = "inp2" type = "password" v-model = "password" required/>
      <div class = "dropdown">
        <label>Role : </label>
        <select v-model = "role">
          <option value = "Web Developer">Web Developer</option>
          <option value = "Data Analyst">Data Analyst</option>
          <option value = "Artificial intelligence engineer">Airtificial intelligence engineer</option>
        </select>
      </div>
      <div class = "terms">
        <input type = "checkbox" class = "chkbox" v-model = "terms" required/>
        <label>Accept Terms and Conditions</label>
      </div>
      <div class = "btn-container">
        <button type = "submit" class = "btn">submit</button>
      </div>
    </form>
    <div v-if = "isDisplay">
      <p>{{ email }}</p>
      <p>{{ password }}</p>
      <p>{{ role }}</p>
      <p>{{ terms }}</p>
    </div>
  </div>
</template>

<script> 
  export default{
    name : "root",
    data(){
      return{
        title : "Form",
        email : "",
        password : "",
        role : "Web Developer",
        terms : false,
        isDisplay : false
      }
    },
    methods : {
      submitHandler(){
        this.isDisplay = true
      }
    }
  }
</script>

<style>
  body{
    background-color: black;
  }

  #frm{
    max-width: 300px;
    margin: 40px auto;
    background-color: #eee;
    padding: 40px;
    padding-top: 10px;
    border-radius: 10px;
  }

  #frm #heading{
    font-family: Verdana, Geneva, Tahoma, sans-serif;
  }

  form{
    max-width: 420px;
    margin: 30px auto;
  }

  form input{
    display: block;
    margin-bottom: 30px;
    width: 292px;
    height: 30px;
    font-size: 15px;
  }

  .btn-container{
    text-align: center;
  }

  .btn-container .btn{
    width: 50%;
    height: 30px;
    border-radius: 3px;
    background-color: #10ABEB;
    color: white;
    border-style: none;
    cursor: pointer;
  }

  #frm p{
    color: black;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
  }

  .dropdown{
    margin-bottom: 30px;
  }

  .dropdown label{
    font-family: Verdana, Geneva, Tahoma, sans-serif;
  }

  .dropdown select{
    width: 75%;
    height: 40px;
    font-size: 15px;
  }

  .terms{
    margin-bottom: 30px;
  }

  .terms .chkbox{
    width: 10px;
    display: inline-block;
    width: 16px;
    margin : 0 10px 0 0;
    position: relative;
    top: 10px;
  }
</style>
