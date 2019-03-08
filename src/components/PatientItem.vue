<template>
    <div class="patient-item" v-bind:class="{'is-complete':patient.attended}">
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{patient.name}}
            <button @click="$emit('del-patient',patient.id)" class="del">x</button>
            </p>
    </div>
</template>
<script>
export default {
    name:"PatientItem",
    props:["patient"],
    methods:{
        markComplete(){
            this.patient.attended=!this.patient.attended;
        }
    }
}
</script>
<style scoped>
.patient-item{
    background: #f4f4f4;
    padding:10px;
    border-bottom:1px #ccc dotted;
}
.is-complete{
    text-decoration: line-through;
}
.del{
    background: #ff0000;
    color: #fff;
    border:none;
    padding:5px 9px;
    border-radius:50%;
    cursor:pointer;
    float:right;
}
</style>
