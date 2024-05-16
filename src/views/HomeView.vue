<script setup>
import { defineComponent, onMounted, ref } from 'vue';
import ImgHover from '@/components/ImgHover.vue';
import User from '../assets/jsons/User.json'
import Project from '../assets/jsons/Project.json'
import StudentCard from '@/components/StudentCard.vue';
import ProjectCard from '@/components/ProjectCard.vue';


const users = ref([]);
onMounted(() => {
  users.value = User;
});

const projects = ref([]);
onMounted(() => {
  users.value = Project;
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
        <StudentCard v-for="(user, index) in User" 
          :key="index" 
          :name="user.name"  
          :lastName="user.lastName"  
          :img="user.img"
          :email="user.email"
          :age="user.age"
          />
      </section>
    </section>

    <section class="proyect-list__container">
      <section class="proyect-list__banner">
        <h2>Aqui encontraras proyectos</h2>
        <p>Esta es la lista de proyectos en los cuales tu como desarrollador podras participar</p>
      </section>
      <section class="projectList">
        <ProjectCard v-for="project in Project" 
          :key="project.projectImg"
          :img="project.projectImg" 
          :name="project.projectName"
          :description="project.description"
          :projectLink="project.projectLink"
          :projectOwner="project.projectOwner"
          />
      </section>
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

/* project */


.proyect-list__container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 3vh;
}

.proyect-list__banner {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.projectList {
  display: flex;
  flex-wrap: wrap;
  gap: 2vw;
}


</style>
