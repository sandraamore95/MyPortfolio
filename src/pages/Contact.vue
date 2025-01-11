

<template>
  <section class="contact py-5">
    <div class="container">
      <h2 class="text-center mb-4">Contactame! </h2>
      <p class="text-center mb-4">
        Si tienes alguna duda no dudes en ponerte en contacto conmigo.
      </p>
      <div class="text-center">
        <a :href="mailtoLink" class="btn btn-secondary">Enviar Correo</a>
      </div>
     
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';

const email = ref('sandra_amoros95@hotmail.com'); 
const subject = ref('Hola!');
const body = ref(''); 

const mailtoLink = `mailto:${email.value}?subject=${encodeURIComponent(subject.value)}&body=${encodeURIComponent(body.value)}`;
</script>

<style scoped>
.contact {
  max-width: 600px;
  margin: auto;
}
</style>
