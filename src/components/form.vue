<template>
    <div class="d-flex flex-column">
       <input class="inp" placeholder="Enter Name" type="text" v-model="formValues.name"><br>
       <input class="inp" type="text" v-model.number="formValues.age"><br>
       <input class="inp" placeholder="Enter Address" type="text" v-model="formValues.address"><br>
       <div class="form-check">
         <input type="checkbox" class="form-check-input " v-model="adminBool" >
         <label class="form-check-label" for="">
           Admin
         </label><br>
         <input type="checkbox" class="form-check-input " v-model="studentBool"  >
         <label class="form-check-label " for="">
           Student
         </label>
       </div>
       
        <button style="width:50px;" class="btn btn-success mt-5" @click="$emit('add',formValues,adminBool,studentBool)">Add</button>

     
       
    </div>
</template>

<script>
    export default {
        name:'formView',
        inject:['errorBool'],
        data(){
            return{
                
               formValues:{ name:'',
                age:0,
                address:'',
                },
               adminBool:false,
                studentBool:false,
                Admins:[],
                Students:[]
            }
        },
        methods:{
            
        }
    }
</script>

<style lang="scss" scoped>
.inp{
    width: 40vw;
    border: 2px solid black;
    height: 40px;
    border-radius: 7px;
}
</style>