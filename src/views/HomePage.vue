<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Crypto List - Tugas 2 MSIM4401 - Agus Setiawan</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Crypto List - Tugas 2 MSIM4401 - Agus Setiawan</ion-title>
        </ion-toolbar>
      </ion-header>

      <div id="container">
        <!-- Button untuk fetch data -->
        <div class="button-container">
          <ion-button @click="fetchCryptoData">Get Data</ion-button>
        </div>

        <!-- Grid untuk menampilkan data -->
        <ion-grid>
          <ion-row class="grid-header">
            <ion-col size="4"><strong>Name</strong></ion-col>
            <ion-col size="4"><strong>Symbol</strong></ion-col>
            <ion-col size="4"><strong>Harga USD</strong></ion-col>
          </ion-row>

          <!-- Loop data crypto -->
          <ion-row v-for="crypto in cryptoList" :key="crypto.id">
            <ion-col size="4">{{ crypto.name }}</ion-col>
            <ion-col size="4">{{ crypto.symbol }}</ion-col>
            <ion-col size="4">{{ crypto.price_usd }}</ion-col>
          </ion-row>
        </ion-grid>

        <!-- Ketika belum ada data -->
        <p v-if="cryptoList.length === 0" class="no-data-message">
          Belum ada data. Silahkan klik "Get Data" untuk mendapatkan cryptocurrency list.
        </p>
      </div>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import axios from 'axios';

// mendefinisikan type data
interface Crypto {
  id: string;
  symbol: string;
  name: string;
  price_usd: string;
}

// State untuk menyimpan data dari API
const cryptoList = ref<Crypto[]>([]);

// fungsi untuk mengambil data dari API
const fetchCryptoData = async () => {
  try {
    const response = await axios.get('https://api.coinlore.net/api/tickers/');
    // mapping data dari API ke dalam bentuk yang diinginkan
    cryptoList.value = response.data.data.map((item: any) => ({
      id: item.id,
      symbol: item.symbol,
      name: item.name,
      price_usd: parseFloat(item.price_usd).toFixed(2), // format to 2 decimal places
    }));
  } catch (error) {
    console.error('Error fetching data:', error);
  }
};
</script>

<style scoped>
#container {
  text-align: center;
  margin-top: 20px;
  padding: 20px;
}

.button-container {
  display: flex;
  justify-content: center;
  margin-bottom: 20px;
}


.grid-header {
  background-color: #333;
  color: #fff;
  font-weight: bold;
}
ion-grid {
  margin-top: 20px;
  border: 1px solid #ddd;
}

ion-row {
  border-bottom: none;
}

ion-col {
  color: #fff;
  padding: 10px;
}
.no-data-message {
  margin-top: 20px;
  color: #666;
  font-size: 16px;
  font-style: italic;
}
</style>
