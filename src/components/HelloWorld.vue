<template>

  <div id="main">
    <div style="padding-top:50px;padding-bottom:50px;">
      Search here: <input type="text" v-model="search" />
    </div>
    <table class="table">
      <thead class="thead-dark">
        <tr>
          <th scope="col">#</th>
          <th scope="col">First</th>
          <th scope="col">Last</th>
          <th scope="col">Handle</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(customer,index) in filteredCustomers">
          <th scope="row">{{customer.id}}</th>
          <td>{{customer.name}}</td>
          <td>{{customer.type}}</td>
          <td>{{customer.email}}</td>
        </tr>
      </tbody>
    </table>
  </div>

</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
       search: '',
        customers: [
            { name: 'Allen Shaji', email: 'allen@gmail.com', type: 'Engineer', id:'1' },
            { name: 'Ashik Shaji', email: 'ashik@gmail.com', type: 'Student',id:'2'},
            { name: 'Sobin Mathew', email: 'asobin@gmail.com', type: 'Footballer',id:'3' },
            { name: 'Junida George', email: 'junida@gmail.com', type: 'Professional',id:'4' },
            { name: 'Aleena Alphonsa', email: 'aleena@gmail.com', type: 'Actor',id:'5' },
            { name: 'Mathew Jose', email: 'mathew@gmail.com', type: 'Actor',id:'6' },
            { name: 'Thomas John',email: 'thomas@gmail.com', type: 'Engineer',id:'7' }]};
    },
 computed:
{
    filteredCustomers:function()
    {
    	 var self=this;
       return this.customers.filter(function(cust){
         return cust.name.toLowerCase().indexOf(self.search.toLowerCase())>=0 || cust.type.toLowerCase().indexOf(self.search.toLowerCase())>=0 || cust.email.toLowerCase().indexOf(self.search.toLowerCase())>=0 || cust.id.indexOf(self.search)>=0;
         });
    }
}
}
</script>

<style scoped>
input[type="text"] {
  width: 250px;
  height: 30px;
  padding-left: 15px;
  border-radius: 6px;
  border: none;
  color: #0f0d0d;
  font-weight: 500;
  background-color: #e2eff7;
  -webkit-box-shadow: 0 -2px 2px 0 rgba(199, 199, 199, 0.55), 0 1px 1px 0 #fff,
    0 2px 2px 1px #fafafa, 0 2px 4px 0 #b2b2b2 inset, 0 -1px 1px 0 #f2f2f2 inset,
    0 15px 15px 0 rgba(41, 41, 41, 0.09) inset;
  -moz-box-shadow: 0 -2px 2px 0 rgba(199, 199, 199, 0.55), 0 1px 1px 0 #fff,
    0 2px 2px 1px #fafafa, 0 2px 4px 0 #b2b2b2 inset, 0 -1px 1px 0 #f2f2f2 inset,
    0 15px 15px 0 rgba(41, 41, 41, 0.09) inset;
  box-shadow: 0 -2px 2px 0 rgba(199, 199, 199, 0.55), 0 1px 1px 0 #fff,
    0 2px 2px 1px #fafafa, 0 2px 4px 0 #b2b2b2 inset, 0 -1px 1px 0 #f2f2f2 inset,
    0 15px 15px 0 rgba(41, 41, 41, 0.09) inset;
}

/* When the input field gets focus, change its width to 100% */
input[type="text"]:focus {
  width: 20%;
}
</style>
