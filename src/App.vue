<template>
  <div class="container">
    <h1 class="title">Selamat Datang Di Halaman Web Saya!!</h1>
    <p class="subtitle">Siapa Nama Kamu?</p>

    <input class="input" type="text" v-model="inputText" placeholder="Ketik Sesuatu..." />

    <div :class="{ 'red-text': isRed }" :style="{ 'font-weight': isBold ? 'bold' : 'normal' }" class="dynamic-text">
      {{ dynamicText }}
    </div>

    <div class="buttons">
      <button @click="toggleRed" class="button">{{ isRed ? 'Nonaktifkan Teks Merah' : 'Nonaktifkan Teks Merah' }}</button>
      <button @click="toggleBold" class="button">{{ isBold ? 'Teks Tebal' : 'Teks Tebal' }}</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputText: '', 
      isRed: false, 
      isBold: false 
    };
  },
  computed: {
    dynamicText() {
      return this.inputText.toUpperCase();
    }
  },
  methods: {
    toggleRed() {
      this.isRed = !this.isRed;
    },
    toggleBold() {
      this.isBold = !this.isBold;
    }
  }
};
</script>

<style scoped>
.container {
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
}

.title {
  font-size: 36px;
  margin-bottom: 20px;
}

.subtitle {
  font-size: 18px;
  margin-bottom: 20px;
}

.input {
  width: 100%;
  padding: 10px;
  margin-bottom: 20px;
  border: 1px solid #d48a8a;
  border-radius: 5px;
  font-size: 16px;
}

.dynamic-text {
  margin-bottom: 20px;
}

.buttons {
  display: flex;
  justify-content: space-between;
}

.button {
  padding: 10px 20px;
  font-size: 12px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  background-color: #4b1a04;
  color: #f3e4e4;
  transition: background-color 0.3s;
}

.button:hover {
  background-color: #854f80;
}

.red-text {
  color: rgb(247, 9, 9)
}
</style>