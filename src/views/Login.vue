



<template >
  <div class="main">
    <div class="menu">
      <button class="menu-btn" @click="showMenu = !showMenu">Menu</button>
      <div v-show="showMenu" class="menu-options">
        <router-link to="/apresentation">
          <button>
            <p class="fa-solid fa-person-chalkboard">Apresentação</p>
            <p>Apresentação</p>
          </button>
        </router-link>

        <router-link to="/catalog">
          <button>
            <p class="fa-solid fa-clipboard">Ficha Catalográfica</p>
            <p>Ficha Catalográfica</p>
          </button>
        </router-link>

        <router-link to="/sources">
          <button>
            <p class="fa-solid fa-magnifying-glass">Fontes</p>
            <p>Fontes</p>
          </button>
        </router-link>
      </div>
    </div>

    <div class="box-login">
      <form @submit.prevent="login()">
        <div class="centralize-box">
          <img
            src="../../public/imgs/PEV-aprovado-pelo-MEC.png"
            id="logo-pev"
          />
          <p class="login-label">HortaTech</p>
        </div>
        <div class="input-box">
          <input
            class="input"
            type="email"
            placeholder="Usuario"
            required
            v-model="email"
          />
          <input
            class="input"
            type="password"
            placeholder="Senha"
            required
            v-model="password"
          />
        </div>
        <p class="signup-label">Não tem uma conta?</p>
        <div class="btn-box">
          <button class="login-btn" @click="login">Entrar</button>
        </div>
       
      </form>
      <p style="color: white;">ISBN 978-65-00-64412-8</p>
    </div>
   
  </div>

  
</template>

<script>
import { signInWithEmailAndPassword } from "firebase/auth";
import { auth } from "../firebase/index.js";
import Header from "../components/Header.vue";
export default {
  data() {
    return {
      email: "",
      password: "",
      displayName: "",
      showMenu: false,
    };
  },

  methods: {
    login() {
      signInWithEmailAndPassword(auth, this.email, this.password).then(() => {
        this.$emit("loggedIn");
        this.$router.push("/home");
      });
    },
  },
  beforeUpdate() {
    if (auth.currentUser) {
      this.displayName = auth.currentUser.displayName;
    }
  },
};
</script>

<style scoped>
.menu {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 999;
}

.menu-btn {
  background-color: transparent;
  border: none;
  font-size: 1.5rem;
  color: white;
  cursor: pointer;
}

.menu-options {
  display: flex;
  flex-direction: column;
  position: absolute;
  top: 3rem;
  left: 0;
  z-index: 999;
  background-color: white;
  border-radius: 0.5rem;
  padding: 1rem;
  box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.2);
}

.menu-options button {
  background-color: transparent;
  border: none;
  font-size: 1rem;
  color: black;
  margin-bottom: 0.5rem;
  cursor: pointer;
}
.main {
  background-image: url(../../public/imgs/TelaLogin.png);
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  justify-content: center;
  align-items: center;
}

#logo-pev {
  width: 100px;
  height: 100px;
}
.box-login {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 35vw;
  height: 40vh;
  border-radius: 50px;
  background-color: #fff;
}
.btn-box {
  display: flex;
  align-items: center;
  justify-content: flex-end;
}

.centralize-box {
  display: flex;
  justify-content: center;
  align-items: center;
}

.input-box {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.input {
  background-color: #064b15;
  border-radius: 30px;
  width: 30vw;
  height: 3.5vh;
  margin: 0.8vw;
  color: #fff;
  padding-left: 10px;
  box-sizing: border-box;
}

.input::placeholder {
  color: #fff;
}

.login-label {
  font-size: 3vw;
  margin: 0px;
}

.login-btn {
  background-color: #064b15;
  color: #fff;
  border-radius: 30px;
  width: 7w;
  height: 5vh;
  font-size: 1.5vw;
}

.signup-label {
  margin-top: 0;
  margin-right: 15vw;
}

@media screen and (max-width: 600px) {
  .box-login {
    width: 75vw;
    height: 22vh;
  }
  .input {
    width: 60vw;
    height: 3vh;
    margin: 0.8vw;
  }
  .login-btn {
    border-radius: 20px;
    width: 12vw;
    height: 4vh;
    font-size: 2.5vw;
  }

  .login-label {
    font-size: 6vw;
    margin: 0px;
  }
}
</style>

