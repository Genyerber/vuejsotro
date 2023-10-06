<template>
  
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" crossorigin="anonymous">
  
  <div>
    <!-- Navbar de Bootstrap -->
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <a class="navbar-brand" href="#">
        <img src="./assets/icons/logo1.jpg" alt="Icono" width="190" height="70" class="d-inline-block align-top">
        
      </a>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item active">
            <a class="nav-link" href="#">Inicio <span class="sr-only">(current)</span></a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Productos</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Contacto</a>
          </li>
          
          
        </ul>
        
      </div>
    </nav>
   
   
  </div>

  <div>
    <!-- Navbar de Bootstrap -->
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <a class="navbar-brand" href="#">
        <img src="@/assets/icons/logo1.jpg" alt="Icono" width="190" height="70" class="d-inline-block align-top">
      </a>
      <!-- ... otros elementos de navegación ... -->

      <!-- Iconos de redes sociales (locales) -->
      <ul class="navbar-nav">
        <li class="nav-item">
          <a class="nav-link" href="#">
            <img src="@/assets/icons/logo2.png" alt="Facebook">
          </a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">
            <img src="@/assets/icons/logo3.png" alt="Instagram">
          </a>
        </li>
        <!-- Agrega más íconos de redes sociales según sea necesario -->
      </ul>
    </nav>
    <!-- Contenido de tu página -->
  </div>

<div id="app">
    
    <camisasProductos/>
    <GorrasProductos/>
    <HoodiesProductos/>
    <PosillosProductos/>
 

  </div>
  


</template>

<script>
// Ejemplo de actualización de importación en App.vue
import camisasProductos from './components/camisasProductos.vue';
import GorrasProductos from './components/GorrasProductos.vue';
import HoodiesProductos from './components/HoodiesProductos.vue';
import PosillosProductos from './components/PosillosProductos.vue';
import data from '@/data.json';
export default {
  components: {
    
    camisasProductos,
    GorrasProductos,
    HoodiesProductos,
    PosillosProductos,

  },
  data() {
      return {
        icons: data.icons,}

},
};


  
 
  
</script>

<style scoped>
/* Estilos CSS globales para la aplicación */
body {
  font-family: Arial, sans-serif;
  
  margin: 0;
  padding: 0;
  background-image: url("./assets/fondos/fondo4.jpg");
        
}

#app {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.product-list {
  margin: 20px;
}

.product {
  background-color: #fff;
  border-radius: 5px;
  padding: 20px;
  margin: 10px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  max-width: 300px;
}

.product img {
  max-width: 100%;
}

.product h3 {
  margin-top: 10px;
}

.product a {
  display: inline-block;
  margin-top: 10px;
  text-decoration: none;
  color: #007bff;
}



</style>
