<template>
  <section class="ImgHover">
      <article>
        <h2>Eres estudiante unimayor?</h2>
        <h2>Ven y mira tu nueva oportunidad de trabajo!</h2>
        <button>Iniciar Sesion</button>
      </article>
    </section>
</template>


<style scoped>
.ImgHover {
  width: 50vw;
  height: 50vh;
  background-image: url('../assets/imgs/Programacion-1000x562.jpeg');
  background-size: cover;
  background-position: center;
  
  /* opacity: 0; Por defecto, el contenido estará oculto */
  /* transition: opacity 0.3s ease; Agregar una transición suave */
}

article {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  padding: 25%;
  text-align: center;
  background-color: rgba(0, 0, 110, 0.644);
  opacity: 0; 
  transition: opacity 0.3s ease;
}

article:hover {
  opacity: 1;
  /* Mostrar el contenido cuando se hace hover en el section padre */
}


.ImgHover h2 {
  font-size: xx-large;
  color: aliceblue;
}

.ImgHover button {
  margin-top: 20px;
}
</style>