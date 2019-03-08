<template>
  <div id="app">
       <!-- {{msg}} -->
      <Header />
      <AddPatient v-on:add-Patient="addPatient"/>
    <Patients v-bind:patients="patients" v-on:del-patient="deletePatient"/>
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Patients from './components/Patients';
import AddPatient from './components/AddPatient';
import axios from 'axios';
export default {
  name: 'app',
  components: {
     Patients,
     Header,
     AddPatient
  },
  data(){
    return{
      //msg:'Hello'
      patients:[]
    }
  },
  methods:{
    deletePatient(id){
      axios.delete(`http://localhost:3000/patients/${id}`)
      .then(res=>this.patients=this.patients.filter(patient => patient.id !== id))
      .catch(err=> console.log(err));
      
    },
    addPatient(newPatient){
      const {id,name,attended }= newPatient;
      axios.post('http://localhost:3000/patients',{
        id,
        name,
        attended
      })
      .then(res => this.patients=[...this.patients,res.data])
      .catch(err => console.log(err));
      
    }
  },
  created(){
    axios.get('http://localhost:3000/patients')
    .then(res => this.patients=res.data)
    .catch(err => console.log(err));
  }
}
</script>

<style>
* {
box-sizing: border-box;
margin: 0;
padding: 0;
}
body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
.btn{
  display:inline-block;
  border:none;
  background: #555;
  color:#fff;
  padding:7px 20px;
  cursor:pointer;
}
.btn:hover{
  background:#666;
}

</style>
