<script setup>
import { ref } from 'vue';

var posts = ref(3)
var followers = ref(100)
var following = ref(100)

var videoUrl = ref("https://www.youtube.com/embed/BN0gBgGBjvs?si=GWtHjycHygGu2pti")

</script>

<template>
    <div class="flex gap-12 mr-10 ml-10 justify-center mt-20 flex-wrap">
        <img class="rounded-full h-64 self-center" src="https://avatars.githubusercontent.com/u/68758638?v=4" alt="github_profile_icon">
        <div class="flex flex-col ml-5">

            <div class="flex gap-5">
                <h3 class="text-2xl self-center">luzakayn</h3>
                <button class="bg-blue-500 text-sm">Seguir</button>
                <button class="text-sm">Enviar Mensagem</button>
            </div>

            <div class="flex justify-between mt-5">

                <div class="flex gap-2">
                    <span class="font-bold">{{ posts }}</span>
                    <span>posts</span>
                </div>
                <!-- <div class="flex gap-2">
                    <span>{{ followers }}</span>
                    <span>followers</span>
                </div>
                <div class="flex gap-2">
                    <span>{{ following }}</span>
                    <span>following</span>
                </div> -->
                
            </div>

            <div class="flex flex-col text-left mt-5">
                <h3 class="text-2xl">vouto</h3>
                <p class="self-right text-gray-400">programmer</p>
            </div>
            
            
            <div class="flex gap-2 mt-2">
                <span>💻</span>
                <span>Desenvolvedor apaixonado por código! PHP, Python, JavaScript, Vue.js</span>
            </div>

            <div class="flex gap-2 mt-2">
                <span>🚀</span>
                <span>Construindo soluções e explorando novas tecnologias.</span>
            </div>

            <div class="flex gap-2 mt-2">
                <span>🌐</span>
                <span>Confira meu portfólio e acompanhe meus projetos!</span>
            </div>

            <div class="flex gap-2 mt-2">
                <span>🗺️</span>
                <span>Minas Gerais, Brazil</span>
            </div>

            <div class="flex gap-2 mt-2">
                <span class="self-center">
                    <svg aria-label="Link icon" class="x1lliihq x1n2onr6 x7l2uk3" fill="currentColor" height="12" role="img" viewBox="0 0 24 24" width="12">
                        <title>Link icon</title>
                        <path d="m9.726 5.123 1.228-1.228a6.47 6.47 0 0 1 9.15 9.152l-1.227 1.227m-4.603 4.603-1.228 1.228a6.47 6.47 0 0 1-9.15-9.152l1.227-1.227" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"></path><line fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" x1="8.471" x2="15.529" y1="15.529" y2="8.471"></line>
                    </svg>
                </span>
                <a href="https://github.com/andradavic" target="_blank">https://github.com/andradavic</a>
            </div>
        </div>
    </div>

    <!-- posts -->
    
    <div class="posts flex flex-col justify-center items-center mt-20">
        <div class="flex gap-3 w-2/3 border rounded border-gray-600 p-5 mr-20 ml-20">
            <img class="rounded-full size-1/12 h-full" src="https://avatars.githubusercontent.com/u/68758638?v=4" alt="">
            <div class="flex flex-col">
                <!-- user details -->
                <div class="flex gap-2 text-2xl flex-wrap">
                    <!-- username -->
                    <span class="font-bold">vouto</span>
                    <!-- user tag + date -->
                    <span class="text-gray-500">@luzakayn - 15 May</span>
                </div>
                <!-- post message -->
                <div class="flex flex-col flex-wrap">
                    <span class="text-2xl text-left">
                        Já é possível sortear times pelo site. <a href="#/roleta">Sortear Agora</a>
                    </span>
                    <img src=".\assets\sorteador.png" alt="">
                </div>
            </div> 
        </div>

        <div class="flex gap-3 w-2/3 border rounded border-gray-600 p-5 mr-20 ml-20">
            <img class="rounded-full size-1/12 h-full" src="https://avatars.githubusercontent.com/u/68758638?v=4" alt="">
            <div class="flex flex-col">
                <!-- user details -->
                <div class="flex gap-2 text-2xl flex-wrap">
                    <!-- username -->
                    <span class="font-bold">vouto</span>
                    <!-- user tag + date -->
                    <span class="text-gray-500">@luzakayn - 15 May</span>
                </div>
                <!-- post message -->
                <div class="flex flex-col flex-wrap">
                    <span class="text-2xl text-left">
                    Terminando esse projeto vou fazer ajustes no app TOMODORO.
                    </span>
                </div>
            </div> 
        </div>

        <div class="flex gap-3 w-2/3 border rounded border-gray-600 p-5 mr-20 ml-20">
            <img class="rounded-full size-1/12 h-full" src="https://avatars.githubusercontent.com/u/68758638?v=4" alt="">
            <div class="flex flex-col">
                <!-- user details -->
                <div class="flex gap- text-2xl flex-wrap">
                    <!-- username -->
                    <span class="font-bold">vouto</span>
                    <!-- user tag + date -->
                    <span class="text-gray-500">@luzakayn - 15 May</span>
                </div>
                <!-- post message -->
                <div class="flex flex-col flex-wrap">
                    <span class="text-2xl text-left">
                    Confira como usar a versão beta do Pomodoro e melhorar sua gestão de tempo ao fazer suas tarefas com TOMODORO!
                    </span>
                    <div class="mt-5">
                        <iframe
                        class="max-w-full"
                        width="560"
                        height="315"
                        :src="videoUrl"
                        frameborder="0"
                        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                        allowfullscreen
                        ></iframe>
                    </div>
                </div>
            </div> 
        </div>
    </div>

    
</template>