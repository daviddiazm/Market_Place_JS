<script setup lang='js'>
import { onMounted, ref, nextTick } from 'vue';

const props = defineProps({
  btnColor: String,
  btnText: String
})

const hoverValue = ref(null)
const myButton = ref(null)
const btnWidth = ref(0)
const btnHeight = ref(0)
const btnColor = ref(props.btnColor || 'orange')
const btnText = ref(props.btnText || 'orange')


const setNumber = (value) => {
  hoverValue.value = value;
  nextTick(getButtonSize);
}


const styleShape = () => {
  return {
    top: hoverValue.value + 'px',
    right: hoverValue.value / 2 + 'px',
    height: btnHeight.value + 'px',
    width: btnWidth.value + 'px',
    backgroundColor: btnColor.value
    // backgroundColor: 'var(btnColor.value)'
  };
}

const getButtonSize = () => {
  if (myButton.value) {
    const button = myButton.value;
    btnWidth.value = button.offsetWidth;
    btnHeight.value = button.offsetHeight;
    // console.log(`Ancho del botón: ${btnWidth.value}px`);
    // console.log(`Altura del botón: ${btnHeight.value}px`);
  }
}

onMounted(() => {
  nextTick(getButtonSize);
});
</script>

<template>
  <div class="btn_componenet">
    <button class="btn" @mouseenter="setNumber(10)" @mouseleave="setNumber(0)" ref="myButton">{{ btnText }}</button>
    <div class="shape" :style="styleShape()"  ></div>
  </div>
</template>

<style scoped>

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
  background-color: rgba(255, 255, 255, 0.521);
  backdrop-filter: blur(5px);

  position: relative;
  z-index: 5;
  padding: 10px;
  border-radius: 15px;
  border: none;
}
.btn:active {
  background-color: rgba(255, 255, 255, 0.817);
}

.shape {
  position: absolute;
  background-color: btnColor;
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