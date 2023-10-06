<template>
  <h2>Posillos</h2>
  
    <div class="product-list">
      
      <div v-for="posillo in posillos" :key="posillo.id" class="product">
        <img :src="require(`@/assets/posillos/${posillo.imagen}`)" alt="Posillo">
        <h3>{{ posillo.nombre }}</h3>
        <p>{{ posillo.descripcion }}</p>
        <a :href="posillo.enlace">Ver detalles</a>
        <p></p><button  type="button" class="btn btn-success" >COMPRAR</button> <p>
       </p><button type="button" class="btn btn-warning">AÑADIR AL CARRITO</button>
      </div>
    </div>
  </template>
  
  <script>
  import data from '@/data.json';
  
  export default {
    data() {
      return {
        posillos: data.posillos,
      };
    },
  };
  </script>
  
  <style scoped lang="scss">
  /* Estilos Sass para el componente Posillos */
  
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
  