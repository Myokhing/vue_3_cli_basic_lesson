<template>
<h1>Modal Box</h1>
  <!-- <h1 ref="greet">Hi</h1>
  <input type="text" ref="name"> 
  <button @click="clickHandler">Click</button>-->
<div v-if="showModal">
    <Modal :header="header" :content="content" :theme="theme" @close="showModal=false">
      <!-- slot html form or template -->
      <h1>Login Success</h1>
      <p>Welcome Ashinindavudha</p>
      <!-- slot name ဖြင့် ပို့နည်း -->
      <template v-slot:link>
        <a href=""> Sign in </a>
        <a href=""> Register </a>
      </template>
    </Modal>
</div>
<!-- teleport -->
<!-- <teleport to=".modal" v-if="showModal">
<Modal :header="header" :content="content" :theme="theme" @close="showModal=false">
     
      <h1>Login Success</h1>
      <p>Welcome Ashinindavudha</p>
      
       <template v-slot:link>
        <a href=""> Sign in </a>
        <a href=""> Register </a>
      </template>
    </Modal>
</teleport> -->
<button @click="showModal=true">Open Modal</button>

<div v-if="showModalTwo">
    <Modal :header="header" :content="content" theme="delete" @close="showModalTwo=false">
      <!-- slot html form or template -->
      <h1>Delete Sure</h1>
      <p>Delete User</p>
      <!-- slot name ဖြင့် ပို့နည်း -->
      <template v-slot:link>
        <a href=""> Sign in </a>
        <a href=""> Register </a>
      </template>
    </Modal>
</div>
<button @click="showModalTwo=true">Delete Modal</button>
</template>
<script>

import Modal from "./components/Modal"
export default {
  data() {
    return {
      header: "Login Success",
      content: "Welcome user Ashin indavudha",
      theme: "success",
      showModal: false,
      showModalTwo: false
    }
  },
  components:{
    //Modal:Modal
    Modal
  },
  methods: {
    clickHandler(){
      // console.log(this.$refs);
      // this.$refs.name.focus();
      // this.$refs.greet.textContent="Greeting"

    },
    openModal() {

    }
  }
}
</script>
<style scoped>
h1{
  color: blue;
}
</style>
