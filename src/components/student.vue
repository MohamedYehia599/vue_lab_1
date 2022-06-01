<template>
    <div>
       <table class="table table-striped ">
           <thead class="thead-inverse|thead-default">
               <tr>
                   <th>Name</th>
                   <th>Age</th>
                   <th>Address</th>
                   <th>Delete</th>
               </tr>
               </thead>
               <tbody>
                   
                   <tr v-for="student in Students" :key="student.name">
                      <td>{{student.name}}</td>
                       <td>{{student.age}}</td>
                       <td>{{student.address}}</td>
                       <td><button class="btn btn-danger" @click="del(student)" >Delete</button></td>
                   </tr>
                  
               </tbody>
       </table>
       
    </div>
</template>

<script>
    export default {
        name:'studentView',
        inject:['Students'],
        methods:{
            del(student){
                
                this.Students.pop(student)
                
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>