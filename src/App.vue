<template>
  <div class="container flex flex-col items-center justify-center min-h-screen p-4 text-center bg-black bg-opacity-80 backdrop-blur-md text-green-300">
    <h1 class="text-3xl font-bold mb-6">Website Antonim Sederhana</h1>
    <input v-model="word" type="text" placeholder="Masukkan kata" 
      class="border border-green-400 p-3 rounded-md bg-transparent text-white placeholder-green-400 focus:outline-none focus:ring-2 focus:ring-green-400" />
    <button @click="findAntonym" 
      class="mt-4 px-6 py-2 text-lg font-semibold text-black bg-green-400 rounded-lg shadow-md hover:bg-green-500 transition-all duration-300">Cari Antonim</button>
    <p v-if="antonym" class="mt-6 text-xl">Antonim: <strong class="text-white">{{ antonym }}</strong></p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      word: '',
      antonyms: {
        "panas": "dingin",
        "besar": "kecil",
        "tinggi": "rendah",
        "cepat": "lambat",
        "gelap": "terang",
        "berani": "penakut",
        "kaya": "miskin",
        "senang": "sedih",
        "keras": "lunak",
        "muda": "tua",
        "aktif": "pasif",
        "murah": "mahal",
        "sukses": "gagal",
        "rapi": "berantakan"
      },
      antonym: ''
    };
  },
  methods: {
    findAntonym() {
      this.antonym = this.antonyms[this.word.toLowerCase()] || "Tidak ditemukan";
    }
  }
};
</script>

<style>
.container {
  max-width: 500px;
  margin: 0 auto;
}
</style>
