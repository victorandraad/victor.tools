<script setup>
import { onMounted } from 'vue';
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
            <div class="flex gap-2 mt-4">
                <button class="text-sm" type="button" @click="">Entrar em contato</button>
                <button class="text-sm" type="button" @click="">Ver meu portfólio</button>
            </div>
        </div>
        <img class="rounded-full" src="https://avatars.githubusercontent.com/u/68758638?v=4" alt="">
    </div>
</template>

<style scoped>
/* Adicione qualquer estilo adicional necessário aqui */
</style>
