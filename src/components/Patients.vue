<template>
    <div>
        <!-- <h1>Patients</h1> -->
        <div v-bind:key="patient.id" v-for="patient in patients">
            <PatientItem v-bind:patient="patient" v-on:del-patient="$emit('del-patient',patient.id)"/>
        </div>
    </div>
</template>
<script>
import PatientItem from './PatientItem.vue';
export default {
  name:"Patients"  ,
  components:{
      PatientItem
  },
  props:["patients"]
}

</script>


<style scoped>

</style>

