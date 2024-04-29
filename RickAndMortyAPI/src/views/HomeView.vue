<script setup>
import { onMounted, reactive, ref } from 'vue';
import ListPersonagens from '../components/ListPersonagens.vue';

let personagens = reactive(ref());

onMounted(() => {
  fetch("https://rickandmortyapi.com/api/character")
  .then(response => response.json())
  .then(response => {
    personagens.value = response.results
    console.log(personagens)
  })
})

</script>

<template>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div>
          <div class="card">
            <div class="card-body row">
              <ListPersonagens
                v-for="personagem in personagens" 
                :nome="personagem.name"
                :status="personagem.status"
                :especie="personagem.species"
                :genero="personagem.gender"
                :localizacao="personagem.location.name"
                :imagem="personagem.image"
                :episodio="personagem.episode">
              </ListPersonagens>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>