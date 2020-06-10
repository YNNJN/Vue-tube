<template>
  <div id="app" class="back">
    <nav class="navbar navbar-expand-lg sticky-top p-5">
      <div class="navbar" style="position: absolute; left: 50%; transform: translateX(-50%);">
        <router-link to="/" class="text-info text-decoration-none pt-5"><strong>Vue-tube</strong></router-link>
      </div>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item">
            <router-link class='nav-link text-info pt-5' to="/movie">Movie</router-link>
          </li>
          <li class="nav-item">
            <router-link class='nav-link text-info pt-5' to="/video">Video</router-link>
          </li>
        </ul>
      </div>
    </nav>

    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 1.3rem;
}

.back {
  min-height: 100vh;
  background: black;
}

.navbar {
  background: black;
}

.nav-item {
  font-size: 0.9rem;
}

</style>
