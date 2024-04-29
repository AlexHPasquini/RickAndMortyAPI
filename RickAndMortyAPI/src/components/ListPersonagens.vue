<script setup>
const personagem = defineProps(["nome", "status", "especie", "genero", "localizacao", "imagem", "episodio"])

</script>

<template>
    <div class="col-md-4">
        <div class="card p-2 mb-2">
            <img :src="personagem.imagem">
            <p class="text-center"><li>Nome: {{ personagem.nome }}</li></p>
            <p class="text-center"><li>Status: {{ personagem.status }}</li></p>
            <p class="text-center"><li>Espécie: {{ personagem.especie }}</li></p>
            <p class="text-center"><li>Genero: {{ personagem.genero }}</li></p>
            <p class="text-center"><li>Localização: {{ personagem.localizacao }}</li></p>
            <p class="text-center"><li>Episódio: {{ personagem.episodio.length }}</li></p>

        </div>
    </div>
</template>

<style>
body {
  background-color: #f0f0f0; 
}
</style>
