<template>
  <div class="hello">
    <div class="list">

</div>

<ul>
  <li>
    <input type="checkbox" id="ckeckbox1">
<input type="text" v-bind:placeholder="placeholderValues.inputQuestion"   id="text1">
<button>Clear List</button>
  </li>

  <li  v-for="(item, index) in duties" v-bind:key="index">
    <span> {{ item.text }} </span>

  </li>


</ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
 data: function(){
   return{
     placeholderValues: {
       inputQuestion: "What do you need to do?"
     },


     duties:[{
       text: 'Learn Vue Js',
     },
     {
       text:'Learn Javascript',
     }
     
     ],
     newDutie: [{
       text:'',
       checked:''
     }]

   }
 }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">


body{
  margin:0;
  padding:0;




.hello{
  border:20px solid #eff1f2;
  max-width:1000px;
  min-width:400px;
  min-height:80px;
  margin:0 auto;
  margin-top:50px;

ul{
  display:inline - block;
  margin:0 auto;
  margin-left: -40px;

 li:first-child{

  // display: block;
  // margin:0 auto;
  display:flex;
  justify-content: space-between;
  align-items: center;
  width:970px;
  text-align: center;
  background-color:#e7e8eb ;
  height: 70px;
  padding:15px;
 }
  

  #checkbox1{
    width:200px; 
    
    
  }

  #text1{
    border:1px groove #d0e5fe;
    border:5px ridge #80b6f5;
    height: 50px;
    width:700px;
    padding-left: 10px;
    border-radius: 1%;
    font-size:15px;
    
  }

  button{
    padding-left: -30px;
    width:100px;
    height:40px;
    background-color:white;
    border:none;
    border:1px solid rgb(145, 137, 137);
  }

  }
}


}



</style>
