<template>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">

  <div class="container d-flex align-items-center justify-content-center">
    <div>
    <div class=" d-flex justify-content-center">
    <button @click="showFormView" class="btn btn-primary mx-3 my-3">Form</button>
    <button @click="showStudentView" class="btn btn-success mx-3 my-3">Students</button>
    <button @click="showAdminView" class="btn btn-danger mx-3 my-3">Admins</button>
    </div>
    
    <div class="main d-flex justify-content-center ">
<admin-view v-if="adminBoolean"/>
  <student-view v-if="studentBoolean"/>
  <form-view @add='add' v-if="formBoolean"/>
    </div>
  
  </div>
  </div>
</template>

<script>
import formView from './components/form.vue'
import studentView from './components/student.vue'
import adminView from './components/admin.vue'
export default {
  name: 'App',
  provide(){
          return {
              Students:this.Students,
              Admins:this.Admins,
              
          }
           
        },
  components: {
    formView,
    studentView,
    adminView
  },
  data(){
  return{
    formBoolean:true,
    adminBoolean:false,
    studentBoolean:false,
    errorBool:false,
    Students:[],
    Admins:[]
  }
},
methods:{
  showFormView(){
    this.formBoolean=true
    this.adminBoolean=false
    this.studentBoolean=false
  },
  showAdminView(){
    this.formBoolean=false
    this.adminBoolean=true
    this.studentBoolean=false
  },
  showStudentView(){
    this.formBoolean=false
    this.adminBoolean=false
    this.studentBoolean=true
  },
  add(formValues,adminBool,studentBool){
    
                if(adminBool){
                    this.Admins.push(formValues)
                }
                else if(studentBool){
                    this.Students.push(formValues)
                }
             

              
             
  }
}
}

</script>

<style>
#app {
 
}
.main{
/* border: 2px solid black; */
width: 40vw;
height: 30vh;
margin: auto;
}
.container{
  height: 80vh;
  width: 80vw;
  border: 2px solid green;
}

</style>
