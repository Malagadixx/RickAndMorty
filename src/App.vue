<script setup>
import {ref} from 'vue'
import {RouterView } from 'vue-router'
</script>

<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark border-bottom border-body fixed-top">
    <div class="container-fluid">
      
      <router-link class="navbar-brand" to="/">Personagens</router-link>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            
            <router-link class="nav-link" aria-current="page" to="/">Início</router-link>
          </li>
          <li class="nav-item">
            
            <router-link class="nav-link" to="/about">Sobre</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>

  <RouterView></RouterView>
</template>

<style>
body{
  background-color: rgb(37, 105, 206);
}
</style>