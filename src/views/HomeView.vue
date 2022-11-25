<template>
  <div class="home">
    <h3>Home Page</h3>
    <!-- <p>Hello {{name}}. You are {{age}} old?</p>
    <input type="text" v-model="name"><br>
    <button @click="handleClick">Click</button>
    <button @click="age++">Increase Age</button> -->
    
    <!-- <h2>Person One</h2>
    <p>Hello {{personOne.name}} - {{personOne.age}}</p>
    <button @click="changeOne">Change one's Name</button>
    <br>
    <h2>Person Two</h2>
    <p>Hello {{personTwo.name}} - {{personTwo.age}}</p>
    <button @click="changeTwo">Change Two's Name</button> -->

    <input type="text" v-model="search">
    <p>search - {{search}}</p>
    <div v-for="name in filtername" :key="name">
      {{name}}
    </div>
  </div>
</template>

<script>
import { reactive, ref } from '@vue/reactivity';
import { computed } from '@vue/runtime-core';
// @ is an alias to /src


export default {
  // setup(){
  //  let name=ref("Rajay");
  //  let age=ref(23)
  //  let handleClick=()=>{
  //   //alert("Your are "+name.value+ " and your age is "+age)
  //   name.value="Anil"
  //  }
  //  return {name, age, handleClick}
  // }

  // setup(){
  //   let personOne=ref({name:"Rajay",age:23});
  //   let changeOne=()=>{
  //     personOne.value.name="Anil"
  //   }

  //   let personTwo=reactive({name:"Rajay Ghimire", age:23});
  //   let changeTwo=()=>{
  //     personTwo.name="Anil karki"
  //   }

  //   return{personOne,changeOne, personTwo,changeTwo}
  // }

  setup(){
    let names=ref(["Rajay","Anil","John","Jimma","July","Halrem","Asus", "Acer"]);
    let search=ref("");
    let filtername=computed(()=>{
      return names.value.filter(name=>{
        return name.includes(search.value)
      })
    })
    return {names,search,filtername}
  }
}
</script>
