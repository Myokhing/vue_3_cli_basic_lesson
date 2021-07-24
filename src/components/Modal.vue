<template>

  <div class="backdrop" @click.self="closeModal">
      <div class="modal" :class="{success:theme==='success', danger:theme==='delete'}">
          
          <!-- props data  -->
          <!-- <h1>{{header}}</h1>
          <p>{{content}}</p> -->
          <!-- parent component မှ slot ဖြင့်ပို့လိုက်သော html or template ကို ဖမ်းနည်း -->
          <slot />
          <!-- slot name ဖြင့် ဖမ်းနည်း -->
          <slot name="link"/>
      </div>
  </div>
</template>

<script>
export default {
props: ['header', 'content', 'theme'],
methods: {
    closeModal() {
        //alert('hi')
        this.$emit("close")
    }
}
}
</script>

<style scoped>
.backdrop {
    position: fixed;
    top: 0;
    background: rgba(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;
}
.modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background-color: white;
    border-radius: 10px;
}
.success {
    background-color: green;
    color: white;
}
.danger{
    background-color: crimson;
    color: white;
}
</style>