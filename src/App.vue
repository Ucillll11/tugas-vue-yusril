<template>
  <div>
    <h1>YUSRIL</h1>
    <h3>Counter: {{ count }}</h3>
    <button @click="incrementkan">Tambah</button>

    <div :style="{ backgroundColor: boxColor }">
      Kotak ini berubah warna.
    </div>
    <button @click="ubahWarna">Ubah Warna</button>

    <div class="carousel">
      <img :src="images[currentIndex]" alt="Gambar Carousel" />
    </div>
    <div class="kontrol-carousel">
      <button @click="prevImage" class="tombol-carousel">Sebelumnya</button>
      <button @click="nextImage" class="tombol-carousel">Selanjutnya</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: 0,
      boxColor: 'blue',
      currentIndex: 0,
      images: [
        'https://picsum.photos/300/200?random=1',
        'https://picsum.photos/300/200?random=2',
        'https://picsum.photos/300/200?random=3'
      ]
    };
  },
  methods: {
    incrementkan() {
      this.count++;
    },
    ubahWarna() {
      this.boxColor = 'red'; // Ubah ke warna yang Anda inginkan
    },
    nextImage() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
    },
    prevImage() {
      this.currentIndex = (this.currentIndex - 1 + this.images.length) % this.images.length;
    }
  }
};
</script>

<style>
body {
  background-color: #d9e2ec;
  /* Warna pastel biru */
}

.carousel {
  width: 320px;
  height: 200px;
  overflow: hidden;
}

.carousel img {
  width: 100%;
  height: 100%;
}

.kontrol-carousel {
  margin-top: 10px;
}

.tombol-carousel {
  padding: 10px 20px;
  font-size: 16px;
  /* Sesuaikan ukuran font sesuai kebutuhan */
  border: 2px solid red;
  border-radius: 5px;
  cursor: pointer;
  margin: 5px;
  /* Sesuaikan margin sesuai kebutuhan */
}
</style>