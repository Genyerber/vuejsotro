<template>
  <h2 class="camiss">Camisas</h2>
       
    <div class="product-list">

       
      <div v-for="camisa in camisas" :key="camisa.id" class="product">
        <img :src="require(`@/assets/camisas/${camisa.imagen}`)" alt="Camisa">
        <h3>{{ camisa.nombre }}</h3>
        <p>{{ camisa.descripcion }}</p>
        <a :href="camisa.enlace">Ver detalles</a><P></P>
        <a href="https://wa.link/gb2ntn" class="btn btn-outline-warning" role="button" >COMPRAR</a>
       
       <div>
    
    <!-- Componente Carrito -->
    <CarritoProductos @producto-agregado="agregarProductoAlCarrito" />
  </div>
      </div>
    </div>
  </template>
  
  <script>
  import data from '@/data.json';
  import CarritoProductos from './CarritoProductos.vue'

  
  export default {
    data() {
      return {
        camisas: data.camisas,
        mostrarCarrito: false, // Variable para controlar la visibilidad del carrito
    
      };
    },
    components: {
      CarritoProductos, // Registra el componente Carrito en este componente
  
    },
    methods: {
    mostrarOcultarCarrito() {
      this.mostrarCarrito = !this.mostrarCarrito; // Cambia el valor de mostrarCarrito al hacer clic en el botón
    },
  },

  };

  
  </script>
  
  <style scoped lang="scss">
  /* Estilos Sass para el componente Camisas */
 
  .product-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    
    .product {
      background-color: #fff;
      border-radius: 8px;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
      margin: 16px;
      max-width: 300px;
      padding: 16px;
      text-align: center;
      transition: transform 0.3s ease-in-out;
      
      &:hover {
        transform: scale(1.05);
      }
      
      img {
        max-width: 100%;
        height: auto;
        border-radius: 4px;
      }
      
      h3 {
        margin-top: 8px;
        font-size: 1.5rem;
      }
  
      
       
      
      p {
        margin-top: 8px;
        font-size: 1rem;
        color: #777;
      }
      
      a {
        display: inline-block;
        margin-top: 12px;
        font-size: 1rem;
        text-decoration: none;
        color: #007bff;
        transition: color 0.3s ease-in-out;
        
        &:hover {
          color: #0056b3;
        }
      }
    }
  }
  </style>
  