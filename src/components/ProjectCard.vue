<script setup lang='js'>
import { ref } from 'vue';

const props = defineProps({
  name: String,
  img: String,
  description: String,
  projectLink: String,
  projectOwner: String,
  ownerName: String,
})
</script>

<template>
  <div class="ProjectCard">
    <img :src="img" alt="">
    <h3>{{ name }}</h3>
    <p>{{ description }}</p>
    <a :href="projectLink">Link del proyecto</a>
    <a :href="projectOwner"> {{ ownerName }} </a>
  </div>
</template>

<style scoped>
.ProjectCard {
  /* Estilo para el contenedor de la tarjeta */
  display: flex; /* Permite que los elementos internos se ordenen en fila */
  flex-direction: column; /* Ordena los elementos uno encima del otro */
  align-items: center; /* Centra los elementos horizontalmente */
  margin: 20px; /* Añade espacio alrededor de la tarjeta */
  padding: 20px; /* Añade espacio dentro de la tarjeta */
  border: 1px solid #ccc; /* Añade un borde gris claro */
  border-radius: 5px; /* Redondea las esquinas de la tarjeta */
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1); /* Añade una sombra sutil */
}

.ProjectCard img {
  /* Estilo para la imagen */
  width: 100%; /* Ocupa todo el ancho disponible */
  height: 200px; /* Ajusta la altura de la imagen */
  object-fit: cover; /* Mantiene la proporción de la imagen y la cubre completamente */
  margin-bottom: 15px; /* Añade espacio debajo de la imagen */
}

.ProjectCard h3 {
  /* Estilo para el título del proyecto */
  font-size: 20px; /* Ajusta el tamaño de la fuente */
  margin-bottom: 10px; /* Añade espacio debajo del título */
}

.ProjectCard p {
  /* Estilo para la descripción del proyecto */
  text-align: justify; /* Justifica el texto */
  line-height: 1.5; /* Añade espacio entre líneas */
  margin-bottom: 15px; /* Añade espacio debajo de la descripción */
}

.ProjectCard a {
  /* Estilo para los enlaces */
  color: #007bff; /* Color azul para los enlaces */
  text-decoration: none; /* Elimina el subrayado por defecto */
  margin-right: 10px; /* Añade espacio entre enlaces */
}

.ProjectCard a:hover {
  /* Estilo para los enlaces al pasar el cursor */
  color: #0056b3; /* Color azul más oscuro al pasar el cursor */
}
</style>