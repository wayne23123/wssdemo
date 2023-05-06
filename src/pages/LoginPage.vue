<script setup>
import { ref, computed } from "vue";

const username = ref("");
const password = ref("");

const loginIn = () => {
  if (username.value != "admin") {
    alert("請確認帳號");
    return;
  }

  if (password.value != "1234") {
    alert("請確認密碼");
    return;
  }
};
</script>

<template>
  <section class="sectionLogin">
    <div class="formLayout">
      <div>
        <div class="formText">請先登入</div>

        <br />

        <div class="inputBox">
          <input v-model="username" type="text" required />
          <span>帳號</span>
        </div>

        <br />

        <div class="inputBox">
          <input v-model="password" type="text" required />
          <span>密碼</span>
        </div>

        <br />
        <br />
        <br />
        <br />

        <router-link @mouseenter="loginIn" to="/admin" class="goAdmin"
          ><button>登入</button>
        </router-link>
      </div>
    </div>
    <div class="imgLayout">
      <img src="../assets/pictures/MatthiasD.png" alt="" />
    </div>
  </section>
</template>

<style scoped>
img {
  width: 100%;
  height: 100%;
}
.sectionLogin {
  height: 100vh;
  width: 100vw;
  max-width: 100%;
  background-color: #000;
  display: flex;
  justify-content: center;
  align-items: center;
  /* background-color: #916800; */
}

.formText {
  color: black;
  display: flex;
  justify-content: center;
  font-size: 25px;
  background-color: #daa520;
  border-radius: 5px;
}

.formLayout {
  position: absolute;
  background-color: #916800;
  padding: 40px;
  border-radius: 15px;
  z-index: 10;
}

button {
  width: 250px;
  height: 40px;
  background-color: #daa520;
  border-radius: 5px;
  font-size: 20px;
}

.inputBox {
  position: relative;
  width: 250px;
}

.inputBox input {
  width: 100%;
  padding: 10px;
  border: 1px solid rgba(255, 255, 255, 0.25);
  background: #1d2b3a;
  border-radius: 5px;
  outline: none;
  color: #fff;
  font-size: 1em;
  transition: 0.5s;
}

.inputBox span {
  position: absolute;
  left: 0;
  padding: 10px;
  pointer-events: none;
  font-size: 1em;
  color: rgba(255, 255, 255, 0.25);
  text-transform: uppercase;
  transition: 0.5s;
}

.inputBox input:valid ~ span,
.inputBox input:focus ~ span {
  color: #00dfc4;
  transform: translateX(10px) translateY(-7px);
  font-size: 0.65em;
  padding: 0 10px;
  background: #1d2b3a;
  border-left: 1px solid #00dfc4;
  border-right: 1px solid #00dfc4;
  letter-spacing: 0.2em;
}

.imgLayout {
  width: 100vw;
  max-width: 100%;
  height: 97vh;
}
</style>
