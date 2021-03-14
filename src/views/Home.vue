<template>
<div class="about" >
  <body background="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAARMAAAC3CAMAAAAGjUrGAAAAA1BMVEUAAACnej3aAAAAR0lEQVR4nO3BAQ0AAADCoPdPbQ8HFAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAPBgxUwAAU+n3sIAAAAASUVORK5CYII=">
  <!-- {{httpdata}} -->
  <div class="container">
    
 <b-card v-for="user in httpdata" :key="user.id">
 <div> {{user.postID}}</div>
 <br>
 <h4>Email: {{user.email}}</h4><br>
 Name: {{user.name}}<br>
  {{user.body}}<br>
  <h2> {{user.type}}</h2>
  <img src=user.iamge alt="">
  
  </b-card>
  
  </div>
  </body>
</div>
  </template>
  

  <script>
    import axios from"axios"; 
    export default {
       data() {
          return { 
            httpdata:""   

             };   
             }, 
             mounted() { 
               axios({ 
                 method:"GET", 
                 url:"http://jsonplaceholder.typicode.com/comments"    })
                 .then(result=> { this.httpdata = result.data;     }); 
                   } };
                  </script>