<script setup lang='js'>
import { nextTick, onMounted, ref } from 'vue';
import ButtonHover from './ButtonHover.vue';


const hoverValue = ref(null)
const myButton = ref(null)
const btnWidth = ref(0)
const btnHeight = ref(0)


const btn1Color = "#F78200";
const btn1Text = "Soy Desarrollador";


// const btn2Color = "--color-ligth-blue-Apple";
const btn2Color = "#009CDF";
const btn2Text = "Soy Cliente";

const setNumber = (value) => {
  // console.log('', hoverValue.value);
  hoverValue.value = value;
  // console.log('', hoverValue.value);
  nextTick(getButtonSize);
}


const styleShape = () => {
  return {
    top: hoverValue.value + 'px',
    right: hoverValue.value / 2 + 'px',
    height: btnHeight.value + 'px',
    width: btnWidth.value + 'px'
  };
}

const getButtonSize = () => {
  if (myButton.value) {
    const button = myButton.value;
    btnWidth.value = button.offsetWidth;
    btnHeight.value = button.offsetHeight;
    console.log(`Ancho del botón: ${btnWidth.value}px`);
    console.log(`Altura del botón: ${btnHeight.value}px`);
  }
}

onMounted(() => {
  nextTick(getButtonSize);
});


</script>

<template>
  <section class="home">
    <div class="blur">
      <div class="logo">
        <!-- logo -->
        <img src="../assets/imgs/camarin_blanco3.png" alt="">
        <h1>UNIMAYOR FREELANCE</h1>
      </div>
      <div class="text__container">
        <!-- texto -->
        <h2>Bienvenido a la nueva experiencia freelance en la unimayor</h2>
      </div>
      <div class="btns_containers">
        <ButtonHover 
          :btnColor="btn1Color"
          :btnText="btn1Text"
        />
        <ButtonHover 
          :btnColor="btn2Color"
          :btnText="btn2Text"
        />
      </div>
    </div>
  </section>
</template>

<style scoped>
.home {
  width: 100vw;
  height: 100vh;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  background-image: url('../assets/imgs/backhround gif white.gif');
  background-position: unset;
  background-repeat: no-repeat;
  background-size: cover;
}

.blur {
  width: 100%;
  height: 100%;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 4vw;

  backdrop-filter: blur(5px);
}

/* logo */
.logo {
  padding: 2vw;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 15px;
  background-color: rgba(240, 248, 255, 0.484);
}

.logo > h1 {
  font-family: 'Audiowide-Regular';
} 


.text__container {
  padding: 2vw;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 250px;
  background-color: rgba(240, 255, 253, 0.687);
}

.btns_containers {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 8vw;
}

.btn_componenet {
  display: flex;
  position: relative;
  justify-content: center;
  align-items: center;
}

.btn {
  background-color: rgba(240, 248, 255, 0.174);
  backdrop-filter: blur(5px);

  position: relative;
  z-index: 5;
  padding: 10px;
  border-radius: 15px;
  border: none;
}

.shape {
  position: absolute;
  background-color: orange;
  color: orange;
  padding: 3px;
  border-radius: 15px;
  right: 3px;
}

/* .btn:hover {
  top: 2px;
  left: 3px;
  bottom: unset;
} */
</style>