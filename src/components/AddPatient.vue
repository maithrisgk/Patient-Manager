<template>
    <div>
        <form @submit="addPatient">
            <input type="text" v-model="name" name="Patient Name" placeholder="Add Patient...">
            <input type="submit" value="Submit" class="btn">

        </form>
    </div>

</template>
<script>
import uuid from 'uuid';
export default {
    name:"AddPatient",
    data(){
        return{
            name:''
        }
    },
    methods:{
        addPatient(e){
            e.preventDefault();
            const newPatient={
                id:uuid.v4(),
                name: this.name,
                attended:false
            }
        //send to parent
        this.$emit('add-Patient',newPatient);

       this.name='';
        }
        
    }
}
</script>
<style scoped>
form{
    display:flex;
}
input[type="text"]{
    flex:10;
    padding:5px;
}
input[type="submit"]{
flex:2;
}
</style>


