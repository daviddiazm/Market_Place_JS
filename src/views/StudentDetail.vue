<script setup lang="js">
import { ref } from 'vue';

const studentInfo = ref({
  name: 'John Doe',
  university: 'University of California, Berkeley',
  major: 'Computer Science',
  whatsapp: '+1234567890',
  github: 'johndoe',
  socialMedia: {
    linkedin: 'https://www.linkedin.com/in/johndoe',
    twitter: 'https://twitter.com/johndoe',
    instagram: 'https://www.instagram.com/johndoe',
  },
  projects: [
    {
      name: 'Project 1',
      description: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam temporibus accusamus aliquid dolore excepturi quae officia, voluptate eveniet ipsam delectus.',
      link: 'https://project1.com',
    },
    {
      name: 'Project 2',
      description: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam temporibus accusamus aliquid dolore excepturi quae officia, voluptate eveniet ipsam delectus.',
      link: 'https://project2.com',
    },
    {
      name: 'Project 3',
      description: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam temporibus accusamus aliquid dolore excepturi quae officia, voluptate eveniet ipsam delectus.',
      link: 'https://project3.com',
    },
  ],
});
</script>

<template>
  <div class="student-info">
    <!-- <h2>{{ studentInfo.value.name }}</h2> -->
    <p>University: {{ studentInfo.value.university }}</p>
    <p>Major: {{ studentInfo.value.major }}</p>

    <div class="contact-info">
      <!-- <a href="https://api.whatsapp.com/send?phone={{ studentInfo.value.whatsapp }}" target="_blank">
        <img src="https://www.freeiconspng.com/images/whatsapp-icon-2" alt="WhatsApp" />
        WhatsApp
      </a>
      <a href="https://github.com/{{ studentInfo.value.github }}" target="_blank">
        <img src="https://icons8.com/icons/set/github" alt="GitHub" />
        GitHub
      </a> -->
      <div class="social-media">
        <!-- <a href="" @click="openSocialMediaLink(studentInfo.value.socialMedia.linkedin)" target="_blank">
          <img src="https://www.freeiconspng.com/img/31484" alt="LinkedIn" />
        </a>
        <a href="" @click="openSocialMediaLink(studentInfo.value.socialMedia.twitter)" target="_blank">
          <img src="https://www.freeiconspng.com/images/twitter-icon-2" alt="Twitter" />
        </a>
        <a href="" @click="openSocialMediaLink(studentInfo.value.socialMedia.instagram)" target="_blank">
          <img src="https://www.freepnglogos.com/pics/logo-ig-png" alt="Instagram" />
        </a> -->
      </div>
    </div>

    <h3>Portfolio</h3>
    <ul class="projects">
      <li v-for="project in studentInfo.value.projects" :key="project.name">
        <h4>{{ project.name }}</h4>
        <p>{{ project.description }}</p>
        <!-- <a href="" @click="openProjectLink(project.link)" target="_blank">View Project</a> -->
      </li>
    </ul>
  </div>
</template>

<style scoped>
.student-info {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.contact-info {
  display: flex;
  align-items: center;
  margin-bottom: 20px;
}

.contact-info a {
  margin-right: 20px;
}

.contact-info img {
  width: 24px;
  height: 24px;
  margin-right: 10px;
}

.social-media {
  display: flex;
  margin-left: auto;
}

.social-media a {
  margin-right: 10px;
}

.social-media img {
  width: 20px;
  height: 20px;
}

.projects {
  list-style: none;
  padding: 0;
}

.projects li {
  margin-bottom: 15px;
  border-bottom: 1px solid #ccc;
  padding-bottom: 10px;
}

.projects h4 {
  margin-top: 0;
  margin-bottom: 5px;
}

.projects a {
  text-decoration: none;
  color: #007bff;
}

</style>