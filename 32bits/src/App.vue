<template>
  <div id="app">
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <div class="container-fluid">
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav">
            <li class="nav-item">
              <router-link :to="{name: 'inicio'}" class="nav-link active" aria-current="page">Inicio</router-link>
            </li>
            <li class="nav-item">
              <router-link :to="{name: 'busqueda'}" class="nav-link active" aria-current="page">Busquedas</router-link>
            </li>
            <li class="nav-item">
              <router-link :to="{name: 'ventas'}" class="nav-link active" aria-current="page">Ventas</router-link>
            </li>
            <li class="nav-item">
              <router-link :to="{name: 'total'}" class="nav-link active" aria-current="page">Total</router-link>
            </li>
          </ul>
        </div>
      </div>
</nav>
    <transition name="vista">
      <router-view></router-view>
    </transition>
  </div>
</template>

<script>

export default {
}
</script>

<style scoped>

.vista-enter-active, .vista-leave-active {
    transition: opacity .1s;
}
.vista-enter, .vista-leave-to{
    opacity: 0;
}
</style>
