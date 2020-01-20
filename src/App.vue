<template>
    <div>
      <div class="m" style="margin:10% 33%;width:400px">
        <br>
        <ejs-multiselect :dataSource='remoteData' 
        :fields='remoteFields' placeholder='Select a name'
        popupWidth="400px"
        popupHeight="200px"
        sortOrder='Descending'>
        </ejs-multiselect>
      </div>
      <footer class="text-center">
        <P> Mohammed a seyam</P>
      </footer>
    </div>
</template>

<script>
import Vue from 'vue';
import{ MultiSelectPlugin } from '@syncfusion/ej2-vue-dropdowns';
Vue.use(MultiSelectPlugin);
import{ DataManager, WebApiAdaptor } from '@syncfusion/ej2-data';
var remoteDataSource = new DataManager({
   url: 'https://ej2services.syncfusion.com/production/web-services/api/Employees',
   adaptor: new WebApiAdaptor,
   crossDomain: true
});
export default Vue.extend({
  data: function() {
    return {
      remoteData: remoteDataSource,
      remoteFields: {text: 'FirstName',  value: 'EmployeeID'},
      dataSource :[
        { Id: 'game1', Game: 'Football' },
        { Id: 'game2', Game: 'Basketball' },
        { Id: 'game3', Game: 'Volleyball' }
      ],
      localFields:{value: 'Id', text: 'Game' }
    };
  }
});

</script>
<style>
@import url(https://cdn.syncfusion.com/ej2/material.css);
footer{
  background-color:brown;
  text-align: center;
  margin: 0.5px;
  padding: 0.5px
}
footer p{
color:bisque
}
.m{
  height: 150px;
}
</style>
