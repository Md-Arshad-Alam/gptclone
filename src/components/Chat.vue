is chat view
<script setup>
import { ref } from "vue";
import NavBar from "../components/NavBar.vue";

const isDropdownOpen = ref(false);
const isOpenMenu = ref(false)
const selectedPlan = ref();

const toggleDropdown = () => {
  isDropdownOpen.value = !isDropdownOpen.value;
};
const openMenu = () => {
  isOpenMenu.value = !isOpenMenu.value;
};
</script>

<template>
  <div
    class="absolute left-0 md:absolute lg:absolute xl:absolute 2xl:absolute z-50"
  >
    <NavBar />
  </div>
  <div class="w-full p-2 ml-0 relative md:ml-80 lg:ml-80 xl:ml-80 2xl:ml-80">
    <div
      class="sticky top-0 mb-1.5 flex items-center justify-between z-10 h-14 p-2 font-semibold bg-token-main-surface-primary"
    >
      <div class="flex items-center justify-between w-full gap-2">
        <button
          @click="openMenu"
          class="block sm:block md:hidden lg:hidden xl:hidden 2xl:hidden"
        >
          <svg
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M3 8C3 7.44772 3.44772 7 4 7H20C20.5523 7 21 7.44772 21 8C21 8.55228 20.5523 9 20 9H4C3.44772 9 3 8.55228 3 8ZM3 16C3 15.4477 3.44772 15 4 15H14C14.5523 15 15 15.4477 15 16C15 16.5523 14.5523 17 14 17H4C3.44772 17 3 16.5523 3 16Z"
              fill="currentColor"
            ></path>
          </svg>
        </button>
        <div v-if="isOpenMenu" class="absolute left-0 top-0">
          <!-- Your dropdown menu content -->
          <NavBar />
        </div>
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
        <div>
          <i class="fa-regular fa-pen-to-square"></i>
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
    <div class="mx-auto w-full relative">
      <div class="flex items-center">
        <div
          class="w-12 h-12 flex items-center justify-center bg-white rounded-full"
        >
          <img class="w-6" src="./icons/p.png" alt="" />
        </div>
        <p class="font-bold">Arshad</p>
      </div>
      <div class="ml-12">
        <p>how to handle</p>
      </div>
      <div class="flex items-center">
        <div
          class="w-12 h-12 flex items-center justify-center bg-white rounded-full"
        >
          <img
            class="w-6"
            src="https://static.vecteezy.com/system/resources/previews/021/059/827/non_2x/chatgpt-logo-chat-gpt-icon-on-white-background-free-vector.jpg"
            alt=""
          />
        </div>
        <p class="font-bold">ChatGPT</p>
      </div>
      <div class="ml-12">
        <p class="mr-2">
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
      <!-- <div
        class="flex fixed left-[50%] bottom-5 right-20 w-96 "
      >
        <div
          class="flex-1 relative border-2 border-gray-300 p-3 rounded-xl flex"
        >
          <input
            type="text"
            class="w-full outline-none"
            placeholder="Message ChatGPT..."
          />
          <div class="flex gap-2">
            <button>➤</button>
          </div>
          <div class="absolute inset-14 left-4 md:left-40 right-4 md:right-40">
            <p class="text-xs text-center">
              ChatGPT can make mistakes. Consider checking important information
            </p>
          </div>
        </div>
      </div> -->
    </div>
  </div>
</template>

<style scoped></style>
