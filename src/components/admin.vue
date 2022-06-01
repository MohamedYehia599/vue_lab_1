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
                   
                   <tr v-for="admin in Admins" :key="admin.name">
                      <td>{{admin.name}}</td>
                       <td>{{admin.age}}</td>
                       <td>{{admin.address}}</td>
                       <td><button class="btn btn-danger" @click="del(admin)" >Delete</button></td>
                   </tr>
                  
               </tbody>
       </table>
    </div>
</template>

<script>
    export default {
        name:'adminView',
        inject:['Admins'],
        methods:{
            del(admin){
                
                this.Admins.pop(admin)
                
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>