<script setup>
import { ref, onMounted } from "vue";

const loaderContainer = ref();

let firstLoaderName = ref();

let loaderBgX = 200;
let loaderBgY = 200;

let toLeft = true;

const firstName = ref("none");
const secondName = ref("none");
const thirdName = ref("none");
const fourthName = ref("none");
const fifthName = ref("none");
const glitch = ref("none");
const glitchA = ref("none");

function render(now) {
  if (now > 1000) {
    firstName.value = "loader__transparent";
  }
  if (now > 1050) {
    firstName.value = "loader__full";
    secondName.value = "loader__transparent";
  }
  if (now > 1100) {
    firstName.value = "loader__transparent";
    secondName.value = "loader__full";
    thirdName.value = "loader__transparent";
  }
  if (now > 1150) {
    firstName.value = "none";
    thirdName.value = "loader__full";
    fourthName.value = "loader__transparent";
  }
  if (now > 1200) {
    fourthName.value = "loader__full";
    fifthName.value = "loader__transparent";
  }
  if (now > 1300) {
    fifthName.value = "none";
    fourthName.value = "loader__transparent";
  }
  if (now > 1350) {
    fourthName.value = "none";
    thirdName.value = "loader__transparent";
  }
  if (now > 1400) {
    thirdName.value = "none";
    secondName.value = "loader__transparent";
  }
  if (now > 1450) {
    secondName.value = "none";
    firstName.value = "loader__transparent";
  }
  if (now > 1500) {
    firstName.value = "loader__full";
  }

  if (toLeft && loaderBgX > -100) {
    loaderBgX--;
    loaderContainer.value.style.background = `radial-gradient(circle at ${loaderBgX}% ${loaderBgY}%, #632f80 0%, #15191f 80%)`;
  } else {
    toLeft = false;
  }
  if (!toLeft && loaderBgX < 200) {
    loaderBgX++;
    loaderContainer.value.style.background = `radial-gradient(circle at ${loaderBgX}% ${loaderBgY}%, #632f80 0%, #15191f 80%)`;
  } else {
    toLeft = true;
  }
  requestAnimationFrame(render);
}

onMounted(() => {
  loaderContainer.value.style.background = `radial-gradient(circle at ${loaderBgX}% ${loaderBgY}%, #632f80 0%, #15191f 80%)`;
  requestAnimationFrame(render);
});
</script>

<template>
  <div class="loader">
    <div ref="loaderContainer" class="loader__container">
      <div ref="firstLoaderName" class="loader__text" :class="firstName">
        ATAV
      </div>
      <div>
        <div
          class="loader__text"
          :class="secondName"
          v-for="item in 4"
          :key="item"
        >
          ATAV
        </div>
      </div>
      <div>
        <div
          class="loader__text"
          :class="thirdName"
          v-for="item in 8"
          :key="item"
        >
          ATAV
        </div>
      </div>
      <div>
        <div
          class="loader__text"
          :class="fourthName"
          v-for="item in 12"
          :key="item"
        >
          ATAV
        </div>
      </div>
      <div>
        <div
          class="loader__text"
          :class="fifthName"
          v-for="item in 16"
          :key="item"
        >
          ATAV
        </div>
      </div>
      <div class="loader__text" :class="glitch">
        AT<span class="none">A</span>V
      </div>
      <div class="loader__text" :class="glitchA">A</div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.none {
  visibility: hidden;
}
.loader {
  &__container {
    width: 100vw;
    height: 100vh;
    & > div {
      position: absolute;
      top: 40%;
      left: 50%;
      transform: translate(-50%, -50%);
    }
    & > div {
      position: absolute;
      top: 40%;
      left: 50%;
      transform: translate(-50%, -50%);
    }
    & > div + div > div {
      position: absolute;
      top: -60px;
      left: 50%;
      transform: translate(-50%, -50%);
    }
    & > div + div > div + div {
      position: absolute;
      top: 0px;
      left: 200px;
      transform: translate(-50%, -50%);
    }
    & > div + div > div + div + div {
      position: absolute;
      top: 60px;
      left: 50%;
      transform: translate(-50%, -50%);
    }
    & > div + div > div + div + div + div {
      position: absolute;
      top: 0;
      left: -200px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div > div {
      position: absolute;
      top: -120px;
      left: -50%;
      transform: translate(-50%, -50%);
    }
    & > div + div + div > div + div {
      position: absolute;
      top: -60px;
      left: -200px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div > div + div + div {
      position: absolute;
      top: 0;
      left: -400px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div > div + div + div + div {
      position: absolute;
      top: 60px;
      left: -200px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div > div + div + div + div + div {
      position: absolute;
      top: 120px;
      left: -50%;
      transform: translate(-50%, -50%);
    }
    & > div + div + div > div + div + div + div + div + div {
      position: absolute;
      top: 60px;
      left: 200px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div > div + div + div + div + div + div + div {
      position: absolute;
      top: 0;
      left: 400px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div > div + div + div + div + div + div + div + div {
      position: absolute;
      top: -60px;
      left: 200px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div + div > div {
      position: absolute;
      top: -180px;
      left: 0;
      transform: translate(-50%, -50%);
    }
    & > div + div + div + div > div + div {
      position: absolute;
      top: -120px;
      left: -200px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div + div > div + div + div {
      position: absolute;
      top: -60px;
      left: -400px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div + div > div + div + div + div {
      position: absolute;
      top: 0px;
      left: -600px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div + div > div + div + div + div + div {
      position: absolute;
      top: 60px;
      left: -400px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div + div > div + div + div + div + div + div {
      position: absolute;
      top: 120px;
      left: -200px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div + div > div + div + div + div + div + div + div {
      position: absolute;
      top: 180px;
      left: 0px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div + div > div + div + div + div + div + div + div + div {
      position: absolute;
      top: 120px;
      left: 200px;
      transform: translate(-50%, -50%);
    }
    &
      > div
      + div
      + div
      + div
      > div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div {
      position: absolute;
      top: 60px;
      left: 400px;
      transform: translate(-50%, -50%);
    }
    &
      > div
      + div
      + div
      + div
      > div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div {
      position: absolute;
      top: 0px;
      left: 600px;
      transform: translate(-50%, -50%);
    }
    &
      > div
      + div
      + div
      + div
      > div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div {
      position: absolute;
      top: -60px;
      left: 400px;
      transform: translate(-50%, -50%);
    }
    &
      > div
      + div
      + div
      + div
      > div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div {
      position: absolute;
      top: -120px;
      left: 200px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div + div + div > div {
      position: absolute;
      top: -240px;
      left: 0;
      transform: translate(-50%, -50%);
    }
    & > div + div + div + div + div > div + div {
      position: absolute;
      top: -180px;
      left: -200px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div + div + div > div + div + div {
      position: absolute;
      top: -120px;
      left: -400px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div + div + div > div + div + div + div {
      position: absolute;
      top: -60px;
      left: -600px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div + div + div > div + div + div + div + div {
      position: absolute;
      top: 0px;
      left: -800px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div + div + div > div + div + div + div + div + div {
      position: absolute;
      top: 60px;
      left: -600px;
      transform: translate(-50%, -50%);
    }
    & > div + div + div + div + div > div + div + div + div + div + div + div {
      position: absolute;
      top: 120px;
      left: -400px;
      transform: translate(-50%, -50%);
    }
    &
      > div
      + div
      + div
      + div
      + div
      > div
      + div
      + div
      + div
      + div
      + div
      + div
      + div {
      position: absolute;
      top: 180px;
      left: -200px;
      transform: translate(-50%, -50%);
    }
    &
      > div
      + div
      + div
      + div
      + div
      > div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div {
      position: absolute;
      top: 240px;
      left: 0;
      transform: translate(-50%, -50%);
    }
    &
      > div
      + div
      + div
      + div
      + div
      > div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div {
      position: absolute;
      top: 180px;
      left: 200px;
      transform: translate(-50%, -50%);
    }
    &
      > div
      + div
      + div
      + div
      + div
      > div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div {
      position: absolute;
      top: 120px;
      left: 400px;
      transform: translate(-50%, -50%);
    }
    &
      > div
      + div
      + div
      + div
      + div
      > div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div {
      position: absolute;
      top: 60px;
      left: 600px;
      transform: translate(-50%, -50%);
    }
    &
      > div
      + div
      + div
      + div
      + div
      > div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div {
      position: absolute;
      top: 0;
      left: 800px;
      transform: translate(-50%, -50%);
    }
    &
      > div
      + div
      + div
      + div
      + div
      > div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div {
      position: absolute;
      top: -60px;
      left: 600px;
      transform: translate(-50%, -50%);
    }
    &
      > div
      + div
      + div
      + div
      + div
      > div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div {
      position: absolute;
      top: -120px;
      left: 400px;
      transform: translate(-50%, -50%);
    }
    &
      > div
      + div
      + div
      + div
      + div
      > div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div {
      position: absolute;
      top: -180px;
      left: 200px;
      transform: translate(-50%, -50%);
    }
    &
      > div
      + div
      + div
      + div
      + div
      > div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div
      + div {
      position: absolute;
      top: 0;
      left: 0;
      transform: translate(-50%, -50%);
    }
    & > div + div + div + div + div + div + div {
      position: absolute;
      top: 46.2%;
      left: 51.14%;
      transform: translate(-50%, -50%);
    }
  }

  &__text {
    @apply text-7xl font-bold;
  }
  &__transparent {
    color: transparent;
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: white;
  }

  &__full {
    color: white;
  }
}
</style>
