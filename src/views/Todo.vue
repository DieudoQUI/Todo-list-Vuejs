<script setup lang="ts">
/* import { count } from 'console'; */
import {ref} from "vue"
import Staricon from "@/components/Staricon.vue"
import Task from "@/components/Task.vue"
import Btn from "@/components/Btn.vue"
const count = ref(0)

const taskList= ref([
    { task: "lessive", isFinish: true, is_important:false},
    { task: "cuisine", isFinish: false,is_important:false},
    { task: "marché", isFinish: true, is_important:false}])
   
   
    function addTodo(){
    taskList.value.push({task:newTask.value,isFinish:false, is_important:false})
    newTask.value=''
    localStorage.setItem('allTask', JSON.stringify(taskList))
  }  
/*   const newTask = ref('')
   function markAsImportant(element){
    element.is_important = !element.is_important
}  */
function supTask(element){
    console.log(element);
    const index = taskList.value.findIndex((item)=> item.task == element.value)
    if(index!=0)
    taskList.value.splice(index,1)
    
}

</script>




<template>
    <div class="wrapper">
        <img src="" alt="">
        <form action="" @submit.prevent="">
            <h1>To-do-list</h1>
            <div id="addTask">
                <input v-model="newTask" type="text" name="" id="newTask" placeholder="Ajoutez une nouvelle tâche ici">
               <!--  <button @click="addTodo" id="addTaskButton">Valider</button> -->
               <Btn @click="addTodo">

                </Btn>
            </div>
        </form>
        <Task @delete="supTask(element)" v-for ="element in taskList" :element="element" id="btn__delete">
          <!--   <input type="type" v-model="newTask"> -->

        </Task>
        

          
    
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
    height: 100vh;
}
.wrapper{
    width: 500px;
 box-shadow: 0px 0px 5px #1a1a1a ;
 margin: 2rem 0 2rem 0;

    
    
}
/* form{
  
} */
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
#addTask button:active, #addTask button:active{
    outline: none;
}

.fieldgroup{
    display: flex;
    padding: .5rem;
}
.fieldgroup input{
  height: 2rem;
}
.fieldgroup label{
    background-color: rgb(101, 101, 65);
    font-size: 1.5rem;
    flex-grow: 1;
}
.active{
    color: white;
   border-color: green;
   text-decoration: line-through;
}
.backgroundColor{
    color: gold;
}
/* #btn__delete{
    background: none;
    border: none;
    background-color: red;
    border: 1px solid red;
    color: #fff;
} */
/* .marque{
    text-decoration: line-through;

} */
/* button{
    display: flex;
    justify-content: center;
    align-items: center;
    padding: .5rem 1rem;
    border: 3px solid transparent;
    background-color: #fff;
} */
</style>