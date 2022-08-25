<script setup lang="ts">
import { ref } from 'vue';
import AppUserData from './AppUserData.vue';
import ViperWallPaper from "../assets/background.jpg"
import RazeWallPaper from "../assets/background2.jpg"

const changeWallPaper = ref(false)
</script>

<template>
  <div class="card">
    <AppUserData />
    <div class="card__container">
      <p @click="changeWallPaper = !changeWallPaper">Mudar plano de fundo</p>
      <div class="card__container-background">
        <img :src="changeWallPaper ? ViperWallPaper : RazeWallPaper" alt="background" />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card {
  width: 100%;
  height: inherit;
  display: flex;

  &__container {
    width: 100%;
    height: 100%;

    p {
      position: absolute;
      left: 31rem;
      color: white;
      cursor: pointer;
      top: 0.5rem;
      user-select: none;
      background-color: rgba(0, 0, 0, 0.068);
    }
  }

  &__container-background {
    height: inherit;
    display: flex;
    justify-content: flex-end;

    img {
      height: inherit;
      width: 85%;
    }
  }

  &__container-logo {
    img {
      position: absolute;
      top: 200px;
      left: 300px;
      height: 300px;
    }
  }
}
/* .logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
} */
</style>