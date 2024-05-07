<script setup>
import ImgHover from '@/components/ImgHover.vue';
import Users from '../assets/jsons/User.json'
import { defineComponent, onMounted, ref } from 'vue';

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
        <section class="StuCard" v-for="(user, index) in users" :key="index">
          <div class="user-info">
            <img :src="user.img" alt="">
            <h3>{{ user.name }} {{ user.lastName }}</h3>
            <p>{{ user.email }}</p>
            <p>{{ user.age }}</p>
          </div>
          <button>Whatsap</button>
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

.StuCard {
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 20px;
  margin-bottom: 20px;
  background-color: #f9f9f9;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.user-info {
  /* Estilos para la información del usuario */
}

.user-info h3 {
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
}

.user-info p {
  font-size: 1rem;
  color: #666;
}
</style>
