<!-- <script lang='js'>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'StudentCard',
  props: {
    name: {
      type: String,
      required: false,
      default: "No tiene nombre"
    },
    lastName: {
      type: String,
      required: false,
      default: "No tiene apellido"
    },
    img: {
      type: String,
      required: false,
      default: "No tiene img"
    },
    age: {
      type: String,
      required: false,
      default: "No tiene edad"
    }
  },
  setup(props) {
    return { props }
  }
})
</script> -->

<script setup>
import { ref } from 'vue';
import { defineProps } from 'vue'; // Import defineProps to access props

// Define the props
const props = defineProps({
  name: String,
  lastName: String,
  email: String,
  img: String,
  age: Number
});

// Use ref with default value
const name = ref(props.name || "No tiene nombre");
const lastName = ref(props.lastName || "No tiene apellido");
const email = ref(props.email || "No tiene email");
const img = ref(props.img || "No tiene img");
const age = ref(props.age || "No tiene edad");
</script>


<template >
  <div class="StuCard">
    <div class="user-info">
      <img :src="img" alt="">
      <h3>{{ name }} {{ lastName }}</h3>
      <p>{{ email }}</p>
      <p>{{ age }}</p>
      <button>Mas detalles</button>
    </div>
  </div>
</template>


<style scoped>

.StuCard {
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 20px;
  margin-bottom: 20px;
  background-color: #f9f9f9;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
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