<template>
  <div class="flex">
    <div
      class="flex flex-col w-full lg:w-[395px] p-[25px] bg-white dark:bg-[#364680] rounded-[20px] mt-[18px] xl:ml-[18px]"
    >
      <!-- Title -->
      <div class="flex justify-between">
        <h3 class="text-[18px] text-[#363E64] dark:text-white">
          Sunrise & Sunset
        </h3>

        <i class="ri-add-circle-line text-[22px] text-[#C3C8DE]"></i>
      </div>

      <!-- locations -->
      <div class="" v-for="(item, index) in allLoc" :key="index">
        <div
          class="flex flex-col w-full bg-[#FFF8F0] dark:bg-[#00000026] rounded-2xl px-[15px] py-5 mt-5"
        >
          <!-- title -->
          <div class="flex justify-between items-center">
            <!-- address -->
            <div class="flex items-center gap-1">
              <i class="ri-map-pin-2-line text-[#5C92FF] text-[18px]"></i>
              <p class="text-[#363E64] dark:text-white text-[15px]">
                {{ item.name }}
              </p>
            </div>

            <div
              class="px-1 hover:cursor-pointer rounded-md transition ease-in-out duration-300 hover:bg-orange-100 dark:hover:bg-gray-800"
            >
              <i class="ri-more-2-line text-[#FFAE52] text-[22px]"></i>
            </div>
          </div>

          <div class="flex justify-between gap-1 lg:px-5">
            <!-- Sunrise -->
            <div class="flex gap-2 items-center">
              <i class="ri-sun-line text-[44px] text-[#FFAE52]"></i>

              <div class="flex flex-col">
                <p class="text-[14px] text-[#C3C8DE]">Sunrise</p>
                <p
                  class="text-[14px] md:text-[16px] font-medium text-[#5C92FF]"
                >
                  {{ item.weathers[0].sunrise.slice(0, 5) }} AM
                </p>
              </div>
            </div>

            <!-- Sunset -->
            <div class="flex gap-2 items-center">
              <i class="ri-moon-line text-[44px] text-[#FFAE52]"></i>

              <div class="flex flex-col">
                <p class="text-[14px] text-[#C3C8DE]">Sunset</p>
                <p
                  class="text-[14px] md:text-[16px] font-medium text-[#5C92FF]"
                >
                  {{ item.weathers[0].sunset.slice(0, 5) }} PM
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      allLoc: [
        {
          country: "Iran",
          id: 100128747,
          locIndex: "first",
          name: "Karaj",
          weathers: [
            {
              date: "2023-04-30",
              description: "partly cloudy",
              humidity: 10,
              icon: "d200",
              sunrise: "05:15:28",
              sunset: "18:51:34",
              temp: 27,
              wind: 16,
            },
            {
              date: "2023-05-01",
              description: "thunderstorms",
              humidity: 14,
              icon: "d240",
              sunrise: "05:14:22",
              sunset: "18:52:25",
              temp: 28,
              wind: 19,
            },
            {
              date: "2023-05-02",
              description: "clear",
              humidity: 9,
              icon: "d000",
              sunrise: "05:13:17",
              sunset: "18:53:15",
              temp: 22,
              wind: 16,
            },
            {
              date: "2023-05-03",
              description: "clear",
              humidity: 11,
              icon: "d000",
              sunrise: "05:12:13",
              sunset: "18:54:06",
              temp: 24,
              wind: 15,
            },
            {
              date: "2023-05-04",
              description: "clear",
              humidity: 15,
              icon: "d000",
              sunrise: "05:11:10",
              sunset: "18:54:56",
              temp: 20,
              wind: 26,
            },
            {
              date: "2023-05-05",
              description: "clear",
              humidity: 7,
              icon: "d000",
              sunrise: "05:10:08",
              sunset: "18:55:46",
              temp: 25,
              wind: 9,
            },
            {
              date: "2023-05-06",
              description: "clear",
              humidity: 7,
              icon: "d000",
              sunrise: "05:09:08",
              sunset: "18:56:37",
              temp: 29,
              wind: 11,
            },
          ],
        },
      ],
    };
  },
};
</script>

<style></style>
