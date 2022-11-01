<template>
  <div class="h-screen relative overflow-hidden">
    {{ search }}
    {{ error }}
    <img src="" />
    <div class="absolute w-full h-full top-0 overlay"></div>
    <div class="absolute w-full h-full top-0 p-48">
      <div class="flex justify-between">
        <div>
          <!-- <h1 class="text-7xl text-white">{{ city.name }}</h1> -->
          <p class="font-extralight text-2xl mt-2 text-white">Sunday Dec 9th</p>
          <!-- <img
            :src="`https://openwealthermap.org/img/wn/${city.wealther[0].icon}@4x.png`"
            class="w-56 icon"
          /> -->
        </div>
        <div>
          <!-- <p class="text-9xl text-white font-extralight">
            {{ city.main.temp }}°
          </p> -->
        </div>
      </div>
      <div class="mt-20">
        <input
          type="text"
          name=""
          class="w-1/2 h-10"
          placeholder="Search a city..."
          v-model="search"
        />
        <button class="bg-sky-400 w-20 text-white h-9">Search</button>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const search = ref("");
const { data: city, error } = useFetch(
  `https://api.openweathermap.org/data/2.5/weather?q=${search}&units=metric&appid=a4356e2119114fc98f26c60fd93ade01`
);
</script>

<style scoped>
.overlay {
  background-color: rgba(0, 0, 0, 0.5);
}
.icon {
  margin-left: -2.75rem;
  margin-top: -2.5rem;
}
</style>
