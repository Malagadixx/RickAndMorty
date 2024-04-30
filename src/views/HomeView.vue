<script setup>
import { onMounted, reactive, ref } from 'vue';
import ListRickandMorty from '@/components/ListRickandMorty.vue';

let rickAndMortys = reactive(ref())

onMounted(() => {
  fetch("https://rickandmortyapi.com/api/character/?page=2")
  .then(response => response.json())
  .then(response => {
    rickAndMortys.value = response.results
    console.log(rickAndMortys)
  });
})

</script>

<template>
  <main>
    <div class="container">
      <div class="row">
        <div class="col">
          <div class="card" style="margin-top: 50px" >
            <img src="https://i.ebayimg.com/images/g/iSwAAOSwXIpjJi76/s-l1600.jpg" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-tittle">Rick and Morty</h5>
              <p class="card-text">O show gira em torno das aventuras dos membros da família Smith, que consiste nos pais Jerry e Beth, seus filhos Summer e Morty, e o pai de Beth, chamado Rick Sanchez, que mora com eles como hóspede. De acordo com Justin Roiland, a família mora fora da cidade de Seattle, no estado norte-americano de Washington.</p>
            </div>
          </div>
        </div>
      <div class="col-md-12"> 
        <div class="card">
          <div class="card-body row">
              <ListRickandMorty v-for="rickAndMorty in rickAndMortys" 
              :key="rickAndMorty.name" 
              :name="rickAndMorty.name" 
              :status="rickAndMorty.status" 
              :gender="rickAndMorty.gender"
              :species="rickAndMorty.species"
              :image="rickAndMorty.image"
              :location="rickAndMorty.location.name"
              :episode="rickAndMorty.episode"/>
            </div>
        </div>
      </div>
     </div>
    </div>
  </main>
</template>

<style>
  .container{
    font-family: sans-serif, serif;
    display: flex;
    gap: 1rem;
    width: 100%;
    margin-left: 50%
  }

</style>