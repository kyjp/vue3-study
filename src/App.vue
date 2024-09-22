<script setup lang="ts">
import { ref } from 'vue'
import FoodCard from './components/FoodCard.vue'
const foods = ref([
  { name: '寿司' },
  { name: 'ハンバーガー' },
  { name: '焼肉' },
  { name: '麵系' },
  { name: 'たこ焼き' },
  { name: 'おでん' },
  { name: '丼系' },
  { name: 'オムライス' },
  { name: 'イタリアン' },
  { name: '中華料理' },
  { name: 'とんかつ' },
  { name: '韓国調理' },
  { name: 'カレー' },
  { name: '鍋系' },
  { name: '居酒屋' },
  { name: 'ファミレス' }
])
const pickedFoodIndex = ref(0)
const newFoodIndex = ref(1)
function pickFood(index) {
  pickedFoodIndex.value = index
  newFoodIndex.value++
}
</script>

<template>
  <main>
    <h1 class="title">今日何食べる？</h1>
    <FoodCard :name="foods[pickedFoodIndex].name" @click="pickFood(pickedFoodIndex)" />
    <template v-if="newFoodIndex < foods.length">
      <p>VS</p>
      <FoodCard :name="foods[newFoodIndex].name" @click="pickFood(newFoodIndex)" />
    </template>
  </main>
</template>

<style scoped>
main {
  width: 350px;
  margin: 100px auto;
  text-align: auto;
}
.title {
  margin-bottom: 60px;
}
</style>
