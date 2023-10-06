<template>
  <div>
  
    
    <!-- Mostrar la lista de productos en el carrito -->
    <ul>
      <li v-for="(producto, index) in carrito" :key="index">
        {{ producto.nombre }} - Cantidad: {{ producto.cantidad }} - Precio: {{ producto.precio * producto.cantidad }}$
        <button @click="eliminarProducto(index)">Eliminar</button>
      </li>
    </ul>
    
    <!-- Mostrar el total del carrito -->
    <div>Total del Carrito: {{ calcularTotal() }}$</div>
    
    <!-- Agregar productos al carrito -->
    <div>
      <select v-model="productoSeleccionado">
        <option v-for="producto in productos" :key="producto.id" :value="producto.id">{{ producto.nombre }}</option>
      </select>
      <input type="number" v-model="cantidad">
      <button @click="agregarProducto">Agregar al Carrito</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      productos: [
        { id: 1, nombre: 'TALLA S', precio: 30000 },
        { id: 2, nombre: 'TALLA M', precio: 30000 },
        { id: 3, nombre: 'TALLA L', precio: 30000 }
      ],
      productoSeleccionado: 1,
      cantidad: 1,
      carrito: []
    };
  },
  methods: {
    agregarProducto() {
      const productoEnCarrito = this.carrito.find(p => p.id === this.productoSeleccionado);

      if (productoEnCarrito) {
        productoEnCarrito.cantidad += parseInt(this.cantidad);
      } else {
        const producto = this.productos.find(p => p.id === this.productoSeleccionado);
        this.carrito.push({
          id: producto.id,
          nombre: producto.nombre,
          precio: producto.precio,
          cantidad: parseInt(this.cantidad)
        });
      }
      
      this.cantidad = 1; // Reiniciar la cantidad a 1 después de agregar un producto
    },
    eliminarProducto(index) {
      this.carrito.splice(index, 1);
    },
    calcularTotal() {
      return this.carrito.reduce((total, producto) => total + (producto.precio * producto.cantidad), 0);
    }
  }
};
</script>
