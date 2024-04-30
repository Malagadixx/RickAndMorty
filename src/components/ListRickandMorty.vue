<script setup>
const rickAndMorty = defineProps(["name", "status", "species", "gender", "location", "image", "episode"])

</script>

<template>
        <div class="card col-md-4">
            <div class="card mb-3"></div>
            <img :src="rickAndMorty.image" class="card-img-top" height="80px" alt="...">
            <div class="card-body">
                <div class="card-tittle text-center">
                <p> Nome: {{ rickAndMorty.name}}</p>
                <p> Status: {{ rickAndMorty.status}}</p>
                <p> Espécie: {{ rickAndMorty.species}}</p>
                <p> Gênero: {{ rickAndMorty.gender}}</p>
                <p> Localização: {{ rickAndMorty.location }}</p>
                <p> Episodios: {{ rickAndMorty.episode.length }}</p>
            </div>
        </div>
    </div>
</template>

<style></style>