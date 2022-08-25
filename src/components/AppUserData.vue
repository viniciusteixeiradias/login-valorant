<script setup lang="ts">
import { ref } from 'vue';


const enable = ref(false)
</script>

<template>
  <div class="app-user-data-card">    
    <div class="app-user-data-card__logo">
      <img src="../assets/logo.png" alt="background" />  
    </div>

    <div class="app-user-data-card__title">
      <p>Fazer login</p>
    </div>


    <div>
      <input class="app-user-data-card__fields" type="text" placeholder="USERNAME" />
    </div>
    <div>
      <input class="app-user-data-card__fields" type="text" placeholder="PASSWORD" />
    </div>

    <div class="app-user-data-card__social">
      <div class="app-user-data-card__social-facebook">
        <img src="../assets/facebook.png" alt="facebook" />
      </div>
      <div class="app-user-data-card__social-google">
        <img src="../assets/google.png" alt="google" />
      </div>
      <div class="app-user-data-card__social-apple">
        <img src="../assets/apple.png" alt="apple" />
      </div>
    </div>
    
    <div class="app-user-data-card__stay-sined-in">
      <input id="checkbox-1"  type="checkbox">
      <label for="checkbox-1">Manter login</label>
    </div>


    <div class="app-user-data-card__submit" :enable="enable">
      <img src="../assets/play-disable.png" alt="play" />
      <input type="button" />
    </div>
    <div class="app-user-data-card__footer">
      <p class="app-user-data-card__footer-create">
        NÃO CONSEGUE INICIAR SESSÃO? <br>
        CRIAR CONTA
      </p>
      <p class="app-user-data-card__footer-version">V20.7.0</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.app-user-data-card {
  padding-inline: 3rem;
  width: 20%;
  height: 100%;
  background-color: white;
  position: absolute;

  &__logo {
    margin-top: 3rem;
    display: flex;
    align-items: center;
    justify-content: center;
    img {
      height: 7rem;
    }
  }

  &__title {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 3rem;
    margin-bottom: 2rem;
    font-size: 1.6rem;
    font-weight: 500;
  }

  &__fields {
    margin-bottom: 1rem;
    width: 100%;
    height: 3.5rem;
    border: none;
    background-color: #EDEDED;
    padding-inline: 1rem;
    border-radius: 5px;
    box-sizing: border-box;

    &:focus {
      background-color: #fff;
      outline: none !important;
      border: 2px solid #FE424F;
    }

    &::placeholder {
      font-weight: 500;
    }
  }

  &__social {
    display: flex;
    gap: 8px;

    div {
      width: 100%;
      height: 2.2rem;
      box-sizing: border-box;
      border-radius: 5px;;
      display: flex;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      margin-bottom: 1rem;

      img {
        height: 1.2rem;
      }
    }

    &-facebook {
      background-color: #136bdd;  

      &:hover {
        background-color: #0060dd;
      }
    }

    &-google {
      background-color: white;
      border: 1px solid rgb(219, 219, 219);  

      &:hover {
        background-color: #f4f4f4;
      }
    }

    &-apple {
      background-color: rgb(12, 12, 12);  

      &:hover {
        background-color: black;
      }
    }
  }

  &__stay-sined-in {
    label {
      cursor: pointer;
      color: gray;
      font-weight: 500;
    }
    input  {
      display: none;
    }

    input + label:before {
      content: "";
      width: 18px;
      height: 18px;
      border-radius: 4px;
      background-color: #EDEDED;
      border: 1px solid #EDEDED;
      display: inline-block;
      vertical-align: middle;
      margin-right: 8px;
      margin-bottom: 3px;
    }

    input:checked + label:before {
      background-image: url("data:image/svg+xml,%0A%3Csvg xmlns='http://www.w3.org/2000/svg' width='18' height='18' viewBox='0 0 10 10'%3E%3Cg class='nc-icon-wrapper' stroke-width='1' fill='%23555555'%3E%3Cpath fill='none' stroke='%23FFFFFF' stroke-linecap='round' stroke-linejoin='round' stroke-miterlimit='10' data-cap='butt' d='M2.83 4.72l1.58 1.58 2.83-2.83'/%3E%3C/g%3E%3C/svg%3E");
      background-color: #FE424F;
      background-position: center;
      border: none;
      padding: 1px;
    }
  }

  &__submit {
    display: flex;
    justify-content: center;
    align-items: flex-end;
    height: 19rem;
    margin-bottom: 4rem;

    input {
      height: 5rem;
      width: 5rem;
      border: none;
      background-color: white;
      border-radius: 25px;
      border: 1px solid #b1b1b1;
      color: #b1b1b1;
    }

    img {
      position: absolute;
      margin-bottom: 1.7rem;
      height: 1.5rem;
    }
  }

  &__footer {
    text-align: center;
    color: gray;
    
    &-create {
      font-size: 1rem;
      cursor: pointer;
      margin-bottom: 1rem;
    }

    &-version {
      font-size: 0.8rem;
      cursor: pointer;
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