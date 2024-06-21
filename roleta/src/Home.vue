<script setup>
import { onMounted, ref } from 'vue';
import Typewriter from 'typewriter-effect/dist/core';

onMounted(() => {
  const typewriter = new Typewriter('#typewriter', {
    loop: true,
    delay: 75,
  });

  typewriter.typeString('Escrevendo sua solução...')
    .pauseFor(5000)
    .deleteAll()
    .start();
});

const portifolio = (() => {
    window.location.href = '#/about'
})

const showMessageModal = ref(false);

const openEmailClient = () => {
    window.open('mailto:victor.daniels@outlook.com.br', '_blank');
};

</script>

<template>
    <div class="flex gap-10 ml-10 mr-10 mt-20 justify-center">
        <div class="flex flex-col gap-3 self-center">
            <h1 id="typewriter"></h1>
            <div class="flex gap-2 self-center mt-5">
                <img class="size-5 self-center" src=".\assets\github.svg" alt="github_icon">
                <a href="https://github.com/andradavic" target="_blank">github.com/andradavic</a>
            </div>
        </div>
    </div>

    <div class="flex ml-10 mr-10 gap-10 mt-20 flex-wrap justify-center">
        <div class="flex flex-col gap-2 w-1/3 justify-center text-left">
            <h3 class="text-2xl">Victor Silva</h3>
            <p>Desenvolvedor apaixonado por tecnologia e inovação.</p>
            <div class="flex gap-2 mt-4 flex-wrap">
                <button class="text-sm" type="button" @click="showMessageModal = true">Entrar em contato</button>
                <button class="text-sm" type="button" @click="portifolio">Ver meu portfólio</button>
            </div>
        </div>
        <img class="rounded-full" src="https://avatars.githubusercontent.com/u/68758638?v=4" alt="">
    </div>

    <!-- Modal para opções de contato -->
    <div v-if="showMessageModal" class="fixed inset-0 bg-gray-600 bg-opacity-75 flex justify-center items-center">
        <div class="flex flex-col p-5 rounded shadow-lg border rounded w-1/3">
            <h3 class="text-xl mb-4">Entre em Contato</h3>
            <button class="bg-blue-500 text-white py-2 px-4 rounded mb-2" @click="openEmailClient">Enviar Email</button>
            <a class="bg-green-500 text-white py-2 px-4 rounded mb-2 text-center" href="https://wa.me/+5531972018637" target="_blank">WhatsApp</a>
            <a class="bg-blue-600 text-white py-2 px-4 rounded mb-2 block text-center" href="https://www.linkedin.com/in/victorandraad" target="_blank">LinkedIn</a>
            <button class="bg-gray-500 text-white py-2 px-4 rounded mt-2" @click="showMessageModal = false">Fechar</button>
        </div>
    </div>
</template>

<style scoped>
/* Adicione qualquer estilo adicional necessário aqui */
</style>
