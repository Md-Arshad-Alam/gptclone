<script setup>
import { ref } from "vue";

const isDropdownOpen = ref(false);
const selectedPlan = ref();

const toggleDropdown = () => {
  isDropdownOpen.value = !isDropdownOpen.value;
};
</script>

<template>
  <div class="w-full p-2 relative">
    <div
      class="sticky top-0 mb-1.5 flex items-center justify-between z-10 h-14 p-2 font-semibold bg-token-main-surface-primary"
    >
      <div class="flex items-center gap-2">
        <div
          class="group flex cursor-pointer items-center gap-1 rounded-xl py-2 px-3 text-lg font-bold hover:bg-gray-100"
          @click="toggleDropdown"
        >
          <div>ChatGPT <span class="text-gray-400">3.5</span></div>
          <button>
            <svg
              width="16"
              height="17"
              viewBox="0 0 16 17"
              fill="none"
              class="text-token-text-tertiary"
            >
              <path
                d="M11.3346 7.83203L8.00131 11.1654L4.66797 7.83203"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
              ></path>
            </svg>
          </button>
        </div>
        <!-- dropdown content -->
        <div
          v-if="isDropdownOpen"
          class="absolute top-14 left-0 bg-white p-2 border rounded-lg w-[340px] shadow-lg"
        >
          <div
            class="flex grow items-center justify-between gap-2 hover:bg-gray-100 p-3 rounded-md"
          >
            <div class="flex items-center gap-3 w-full">
              <div class="flex-shrink-0">
                <img
                  class="w-4"
                  src="./icons/christmas-stars_61191.png"
                  alt=""
                />
              </div>
              <div class="flex-grow">
                <div>
                  GPT-3.5
                  <div class="text-gray-400 text-xs">
                    Great for everyday tasks
                  </div>
                </div>
              </div>
              <div class="text-right">
                <input
                  class="size-4"
                  type="radio"
                  v-model="selectedPlan"
                  :value="'GPT-3.5'"
                />
              </div>
            </div>
          </div>
          <div
            class="flex grow items-center justify-between gap-2 hover:bg-gray-100 p-3 rounded-md"
          >
            <div>
              <div class="flex items-center gap-3">
                <div class="">
                  <img
                    class="w-6"
                    src="./icons/christmas-stars_61191.png"
                    alt=""
                  />
                </div>
                <div>
                  GPT-4
                  <div class="text-gray-400 text-xs">
                    Our smartest and most capable model. Includes DALL·E,
                    browsing and more.
                    <div class="mt-2">
                      <button
                        class="w-full bg-purple-500 text-white p-2 rounded-lg"
                      >
                        Upgrade to Plus
                      </button>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="text-right">
              <input
                class="size-4"
                type="radio"
                v-model="selectedPlan"
                :value="'GPT-3.5'"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- <h1 class="text-black font-bold font-sans text-lg">ChatGPT 4</h1> -->
    <!-- <div
        class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2"
      > -->
    <div class="mx-auto w-[790px] ">
      <div class="flex items-center">
        <div
          class="w-12 h-12 flex items-center justify-center bg-white rounded-full"
        >
          <img class="w-6" src="./icons/p.png" alt="" />
        </div>
        <p class="font-bold">Arshad</p>
      </div>
      <div class="ml-12">
        <p>
         how to handle 
         
        </p>
      </div>
      <div class="flex items-center">
        <div
          class="w-12 h-12 flex items-center justify-center bg-white rounded-full"
        >
          <img class="w-6" src="https://static.vecteezy.com/system/resources/previews/021/059/827/non_2x/chatgpt-logo-chat-gpt-icon-on-white-background-free-vector.jpg" alt="" />
        </div>
        <p class="font-bold">ChatGPT</p>
      </div>
      <div class="ml-12">
        <p>
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Labore autem
          impedit suscipit atque laboriosam quasi nam culpa architecto ad
          consequuntur dolore hic rem odio soluta consectetur totam quo,
          voluptatum possimus?
        </p>
      </div>
      <!-- <div class="">
          <div
            class="flex h-full flex-col items-center justify-center text-token-text-primary bg-white rounded-full"
          >
            <img
              class="w-10 rounded-full"
              src="https://static.vecteezy.com/system/resources/previews/021/059/827/non_2x/chatgpt-logo-chat-gpt-icon-on-white-background-free-vector.jpg"
              alt=""
            />
          </div>
          <h2 class="text-center mb-5 text-2xl font-medium">
            How can I help you today?
          </h2>
        </div> -->

      <!-- <div
          class="max-w-min mx-auto mt-4 flex flex-col lg:flex-row justify-between gap-2 lg:gap-8"
        >
          <div class="">
            <div class="border-2 rounded-lg mb-4 px-3 py-1 items-start w-8/2">
              <div class="truncate">Create a charter</div>
              <div class="truncate font-normal opacity-50">
                to start a film club "orders" table
              </div>
            </div>
            <div class="border-2 rounded-lg mb-4 px-3 py-1 items-start w-8/2">
              <div class="truncate">Write a spreadsheet formula</div>
              <div class="truncate font-normal opacity-50">
                to convert a date to the weekday "orders" table
              </div>
            </div>
          </div>
          <div class="">
            <div class="border-2 rounded-lg mb-4 px-3 py-1 items-start w-8/2">
              <div class="truncate">Write a text</div>
              <div class="truncate font-normal opacity-50">
                inviting my neighbors to a barbecue
              </div>
            </div>
            <div class="border-2 rounded-lg mb-4 px-3 py-1 items-start w-8/2">
              <div class="truncate">Write a SQL query</div>
              <div class="truncate font-normal opacity-50">
                that adds a "status" column to an "orders" table
              </div>
            </div>
          </div>
        </div> -->
    </div>
    <div class="flex absolute bottom-8 left-60 right-60 b">
      <div class="flex-1 relative border-2 border-gray-300 p-3 rounded-xl flex">
        <input
          type="text"
          class="w-full outline-none"
          placeholder="Message ChatGPT..."
        />
        <div class="flex gap-2">
          <button>➤</button>
        </div>
      </div>
    </div>
    <div class="absolute bottom-2 left-40 right-40">
      <p class="text-xs text-center">
        ChatGPT can make mistakes. Consider checking important information
      </p>
    </div>
  </div>
</template>

<style scoped></style>
