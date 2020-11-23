<template>
  <div id="nav">
    <router-link to="/">Inicios</router-link> ||
    <router-link to="/about">A serca de nosotros</router-link>||
    <router-link to="/actividad">Actividades</router-link>||
    <router-link to="/contacto">Contactenos</router-link>||
    <router-link to="/blog">Nuestro Blog</router-link>||
    <router-link to="/tienda">Nuestra Tienda</router-link>
  </div>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
