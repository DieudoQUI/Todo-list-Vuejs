<script setup lang="ts">
/* import { count } from 'console'; */
import {ref} from "vue"
const count = ref(0)
let taskList= [{new:"alk"},
    {id : 1, task: "lesive", isFinish: true},
    {id : 2, task: "cuisine", isFinish: false},
    {id : 3, task: "marché", isFinish: true}]
    const addTaskButton = document.getElementById('addTaskButton')
    let newTask = document.getElementById('newTask')
    console.log(addTaskButton);
    
    console.log(newTask);
    
    console.log(addTaskButton);
    
</script>




<template>
    <div class="wrapper">
        <form action="">
            <h1>To-do-list</h1>
            <div id="addTask">
                <input v-model="taskList[0].task" type="text" name="" id="newTask" placeholder="Ajoutez une nouvelle tâche ici">
                <button id="addTaskButton">Valider</button>
            </div>
            <div :class="element.isFinish?'active': ''" v-for ="element in taskList" class="fieldgroup">
                <label class="marque" for="one">{{element.task}}  </label>
                <input type="checkbox" id="one" v-bind:checked="element.isFinish">
               
            </div>
           
    
          
        </form>
       <!--  <button @click ="count++">
            {{ count  }}
        </button>
 -->
    </div>
</template>
<style>


body{
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgb(86, 86, 71);
}
.wrapper{
    width: 500px;
 /*    height: 700px; */
    
    
}
form{
    vertical-align: middle;

    box-shadow: 0px 0px 5px #1a1a1a ;

}
form h1{
    text-align: center;
}
#addTask{
    display: flex;
    padding: 0.5rem;
}
#addTask input{
   /*  flex: 1 1 50px; */
    flex-grow: 1;
    border-top-left-radius: 12px;
    border-bottom-left-radius: 12px;
    outline: none;
    border: none;
  
    padding: .5rem;
    color: #1a1a1a;
    font-size: 1rem;

    

}
#addTask input::placeholder{

   /*  padding: .5rem; */
    color: #1a1a1a;
    font-size: 1rem;

}
#addTask button{
    background-color: gray;
    cursor: pointer;
    padding: .5rem 1rem;
    border: 3px solid transparent;
    font-size: 1rem;
    color: #fff;
    font-weight: bold;
   
}

.fieldgroup{
    display: flex;
    padding: .5rem;
}
.fieldgroup label{
    flex-grow: 1;
}
.fieldgroup label{
    background-color: rgb(101, 101, 65);
    font-size: 1.5rem;
}
.active{
    color: white;
   border-color: green;
}
.marque{
    text-decoration: line-through;
 /*    background-color: green; */
}
/* button{
    display: flex;
    justify-content: center;
    align-items: center;
    padding: .5rem 1rem;
    border: 3px solid transparent;
    background-color: #fff;
} */
</style>