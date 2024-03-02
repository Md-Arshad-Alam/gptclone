<!-- Navbar.vue section -->
<script setup>
import { ref } from "vue";

const isCloseMenu = ref(false);
const closeMenu = () => {
  isCloseMenu.value = !isCloseMenu.value;
};
</script>

<template>
  <div class="flex">
    <div v-if="!isCloseMenu" class="p-4 w-80 bg-gray-100 h-[100vh] relative">
      <div
        class="flex justify-between items-center hover:bg-gray-200 p-2 rounded-md"
      >
        <div class="flex items-center">
          <span
            ><img
              class="w-6 rounded-full"
              src="https://static.vecteezy.com/system/resources/previews/021/059/827/non_2x/chatgpt-logo-chat-gpt-icon-on-white-background-free-vector.jpg"
              alt=""
          /></span>
          <h4 class="px-2 font-bold text-sm">New chat</h4>
        </div>
        <div><i class="fa-regular fa-pen-to-square"></i></div>
      </div>
      <div class="absolute top-0 inset-80 h-lvh">
        <button
          @click="closeMenu"
          class="block sm:block md:hidden lg:hidden xl:hidden 2xl:hidden  bg-black bg-opacity-50"
        >
          <svg
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
            class="icon-md"
          >
            <path
              d="M6.34315 6.34338L17.6569 17.6571M17.6569 6.34338L6.34315 17.6571"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            ></path>
          </svg>
        </button>
      </div>
      <div class="absolute bottom-8 left-5 right-0">
        <div class="flex items-center gap-2 w-full">
          <div
            class="w-8 h-8 flex items-center justify-center bg-white rounded-full"
          >
            <img class="w-4" src="./icons/christmas-stars_61191.png" alt="" />
          </div>
          <div class="w-full">
            <h3 class="font-medium text-sm">Upgrade plan</h3>
            <p class="text-gray-400 text-xs">Get GPT-4 DALL-E and more</p>
          </div>
        </div>
        <div class="mt-5 flex">
          <div
            class="w-8 h-8 flex items-center justify-center bg-white rounded-full"
          >
            <img class="w-4" src="./icons/p.png" alt="" />
          </div>
          <button>User</button>
        </div>
      </div>
    </div>
    <Chat v-else />
  </div>
</template>

<style scoped></style>
