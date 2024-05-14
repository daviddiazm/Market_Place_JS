<script setup>
import { defineComponent, onMounted, ref } from 'vue';
import ImgHover from '@/components/ImgHover.vue';
import Users from '../assets/jsons/User.json'
import StudentCard from '@/components/StudentCard.vue';

const users = ref([]);
onMounted(() => {
  users.value = Users;
});
</script>

<template>
  <main>
    <section class="home__stu-rep">
      <ImgHover />
      <ImgHover />
    </section>

    <section class="stu-list__container">
      <article class="stu-list__banner">
        <h2>Encuentra Los mejores programadores</h2>
        <p>Tenemos una variedad de perfiles dentro de los que estan estudiantes, egresados, profesionales, que se enfocan en una gran variedad de tecnologias dispuestos a colaborar con usted</p>
      </article>
      <section class="stuList">
        <StudentCard v-for="(user, index) in Users" 
          :key="index" 
          :name="user.name"  
          :lastName="user.lastName"  
          :img="user.img"
          :email="user.email"
          :age="user.age"
          />
      </section>
      <section class="projectList">
        <section class="ProjectCard">
          <img src="" alt="">
          <h3>Nombre del proyecto</h3>
          <p>Descripcion</p>
          <a href="#">Link del proyecto</a>
          <a href="#">Nombre del autor</a>
        </section>
      </section>
    </section>

    <section class="proyect-list__container">

    </section>
  </main>
</template>

<style scoped>
.home__stu-rep {
  display: flex;
}

.stu-list__container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 3vh;
}

.stu-list__banner {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.stuList {
  display: flex;
  flex-wrap: wrap;
  gap: 2vw;
}
</style>
