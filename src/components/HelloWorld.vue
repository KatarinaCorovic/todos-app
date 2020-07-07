<template>

  <div class="hello">
    
<ul>
  <li>
    <input type="checkbox" id="checkbox1" name="checkbox1" v-model="newTask.checked">
    <input type="text" v-bind:placeholder="placeholderValues.inputQuestion"  v-model="newTask.text" v-on:keyup.enter="addNewTask" name="newTask" id="newTask">
    <button v-on:click="removeAllTasks" id="buttonClearAll"> Clear List</button>
  </li>

  <li  v-for="(item, index) in tasks" v-bind:key="index">
    <input type="checkbox" v-model="item.checked" name="checkbox" id="checkbox">
    <span> {{ item.text }} </span>
    <button id="buttonRemoveTask" v-on:click="removeTask(index)">x</button>
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
     tasks:[{
       text: 'Learn Vue Js',
       checked:false
     },
     {
       text:'Learn Javascript',
       checked:true
     }
     
     ],
     newTask: [{
       text:'',
       checked:''
     }]
   }
 },


methods:{
  addNewTask: function (){
    this.tasks.unshift({
      text: this.newTask.text,
      checked: this.newTask.checked
    });

    this.newTask.text="",
    this.newTask.cheched=false
  },

  removeTask: function(taskIndex){
    this.tasks.splice(taskIndex, 1);
  },

  removeAllTasks: function(){
    this.tasks.splice(0,this.tasks.length);
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

 li{

  // display: block;
  // margin:0 auto;
  list-style-type: none;
  display:flex;
  justify-content: space-around;
  align-items: center;
  width:970px;
  text-align: center;
  background-color:#3564a4;
  height: 70px;
  padding:15px;
  font-size:25px;
  color:#fff;
  font-family: 'Arial', sans-serif;
  position: relative;
  
  

  &:first-child{
    background-color: #e7e8eb ;
  }
 
  #checkbox1{
    width:20px;
    height:20px; 
    cursor: pointer;
   
  }

  #newTask{
    border:1px groove #d0e5fe;
    border:5px ridge #80b6f5;
    height: 50px;
    width:700px;
    padding-left: 10px;
    border-radius: 1%;
    font-size:20px;
    
  }

  #buttonClearAll{
    padding-left: -30px;
    width:120px;
    height:50px;
    background-color:white;
    border:none;
    border:1px solid rgb(145, 137, 137);
    font-size:20px;
    cursor: pointer;
  }

   span{
     display: inline-block;
     width:970px;
    //  display:flex;
    //  justify-content: left;
     text-align: left;
     margin-left: 41px;
       
  }

  #buttonRemoveTask{
    // opacity: 0%;
    background-color: #3564a4;
    border:none;
    font-size: 25px;
    font-weight: bold;
    color:maroon;
    position: absolute;
    top:30px;
    right: 70px;
    
    &:hover{
      cursor:pointer;
      
    }
  }
  &:hover #buttonRemoveTask{
    opacity:100%;
    border:none;
  }

  #checkbox{
    width:20px;
    height:20px;
    margin-left: 21px;
    cursor: pointer;
  }


  }
}
}


}

</style>
