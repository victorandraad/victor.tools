<template>
    <div class="pl-10 flex flex-col justify-center">
        <div class="flex-column text-start w-3/4 pt-20">
            <h2 class="text-2xl">Como funciona o sorteio de times</h2>
            <p>Essa ferramente oferece uma maneira fácil e eficiente de sortear times para jogos. Basta seguir alguns passos simples e você terá os tiomes definidos rapidamente</p>
        </div>

        <div class="flex gap-12 pt-20 spacebetween flex-wrap">
            <div class="flex flex-col gap-2 text-start">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="size-10">
                    <path d="M12.378 1.602a.75.75 0 0 0-.756 0L3 6.632l9 5.25 9-5.25-8.622-5.03ZM21.75 7.93l-9 5.25v9l8.628-5.032a.75.75 0 0 0 .372-.648V7.93ZM11.25 22.18v-9l-9-5.25v8.57a.75.75 0 0 0 .372.648l8.628 5.033Z" />
                </svg>
                <h2>Passo a passo do sorteio</h2>
                <p>1. Insira o número de times e jogadores.</p>
            </div>

            <div class="flex flex-col gap-2 text-start ">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="size-10">
                    <path d="M12.378 1.602a.75.75 0 0 0-.756 0L3 6.632l9 5.25 9-5.25-8.622-5.03ZM21.75 7.93l-9 5.25v9l8.628-5.032a.75.75 0 0 0 .372-.648V7.93ZM11.25 22.18v-9l-9-5.25v8.57a.75.75 0 0 0 .372.648l8.628 5.033Z" />
                </svg>
                <h2>Resultados imediatos</h2>
                <p>2. Clique em 'Sortear' para obter os times.</p>
            </div>
            
            <div class="flex flex-col gap-2 text-start">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="size-10">
                    <path d="M12.378 1.602a.75.75 0 0 0-.756 0L3 6.632l9 5.25 9-5.25-8.622-5.03ZM21.75 7.93l-9 5.25v9l8.628-5.032a.75.75 0 0 0 .372-.648V7.93ZM11.25 22.18v-9l-9-5.25v8.57a.75.75 0 0 0 .372.648l8.628 5.033Z" />
                </svg>
                <h2>Flexibilidade e personalização</h2>
                <p>3. Ajuste as configurações de acordo com suas preferências.</p>
            </div>
        </div>

        <div class="flex gap-12 mt-20">
            <button class="self-center text-white" @click="navigateToRoleta">Expiremente agora ></button>
        </div>
    </div>
    
</template>

<script setup>
const navigateToRoleta = () => {
  window.location.href = '#/roleta'
};
</script>

<style scoped>
    h2{
        font-size: 20px;
        font-weight: bold;
    }
    h1{
        font-weight: bold;
    }

    .spacebetween{
        justify-content: space-between;
    }
</style>