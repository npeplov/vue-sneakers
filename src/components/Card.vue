<script setup>
// import { inject } from 'vue'
const props = defineProps({
  imageUrl: String,
  title: String,
  price: Number,
  isFavorite: Boolean,
  isAdded: Boolean,
  onClickFavorite: Function,
  onClickAdd: Function,
  id: Number
})
console.log(props.onClickFavorite)
</script>

<template>
  <div
    class="relative bg-white border-slate-100 transition rounded-3xl p-8 cursor-pointer hover:-translate-y-2 hover:shadow-xl"
  >
    <img
      v-if="onClickFavorite"
      @click="onClickFavorite"
      class="absolute left-8 top-8"
      :src="!isFavorite ? '/like-1.svg' : '/like-2.svg'"
      alt=""
    />
    <img :src="imageUrl" alt="Sneaker" />
    <p class="mt-2">{{ title }}</p>
    <div class="flex justify-between mt-5">
      <div class="flex flex-col">
        <span class="text-slate-400">Цена:</span>
        <b>{{ price }} руб</b>
      </div>
      <img
        v-if="onClickAdd"
        @click="onClickAdd"
        :src="!isAdded ? '/plus.svg' : '/checked.svg'"
        alt=""
      />
    </div>
  </div>
</template>
