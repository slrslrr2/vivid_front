<template>
  <Skeleton
    v-if="!weathers"
    :count="7"
    width="120px"
    height="168px"
    class="flex justify-center gap-5 flex-wrap lg:justify-between mt-11"
  />

  <div
    v-else
    class="flex justify-center gap-5 flex-wrap lg:justify-between mt-11"
  >
    <div
      v-for="(day, index) in weathers"
      :key="index"
      class="w-[120px] h-[168px] pt-5 bg-white dark:bg-[#364680] rounded-[20px] flex flex-col items-center text-[18px] text-[#363E64] dark:text-white day-hover"
      :class="[
        background,
        {
          'day-active ': index == active.id,
          'border-b-4 border-red-500': index == 0,
        },
      ]"
      @click="activeDay(index)"
    >
      <img
        :src="
          'https://www.foreca.com/public/images/symbols/' + day.icon + '.svg'
        "
        :alt="day.description"
        class="w-[70px] h-[70px] -mt-1"
      />
      <p class="mt-2">
        {{ new Date(day.date).toLocaleDateString("en", { weekday: "short" }) }}
      </p>
      <p class="font-medium">{{ day.temp }}°</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      weathers: [
        {
          date: "2023-04-30",
          description: "thunderstorms",
          humidity: 15,
          icon: "d240",
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
          humidity: 13,
          icon: "d000",
          sunrise: "05:13:17",
          sunset: "18:53:15",
          temp: 22,
          wind: 16,
        },
        {
          date: "2023-05-03",
          description: "clear",
          humidity: 10,
          icon: "d000",
          sunrise: "05:12:13",
          sunset: "18:54:06",
          temp: 24,
          wind: 15,
        },
        {
          date: "2023-04-30",
          description: "thunderstorms",
          humidity: 15,
          icon: "d240",
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
          humidity: 13,
          icon: "d000",
          sunrise: "05:13:17",
          sunset: "18:53:15",
          temp: 22,
          wind: 16,
        },
        {
          date: "2023-04-30",
          description: "thunderstorms",
          humidity: 15,
          icon: "d240",
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
          humidity: 13,
          icon: "d000",
          sunrise: "05:13:17",
          sunset: "18:53:15",
          temp: 22,
          wind: 16,
        },
      ],
      active: {
        date: "2023-04-30",
        description: "partly cloudy",
        humidity: 10,
        icon: "d200",
        id: 0,
        sunrise: "05:15:28",
        sunset: "18:51:34",
        temp: 27,
        wind: 16,
        background: "from-[#9CBDFF] to-[#6498FF]",
      },
      locIndex: "first",
    };
  },
  computed: {
    background() {
      // change background when change location
      let background;

      switch (this.locIndex) {
        case "first":
          background = "from-[#9CBDFF] to-[#6498FF]";
          break;
        case "second":
          background = "from-[#FD9AC0] to-[#FF649D]";
          break;
        case "third":
          background = "from-[#FFC480] to-[#FFAE52]";
          break;
      }

      return background;
    },
  },
  methods: {
    activeDay(index) {},
  },
};
</script>

<style></style>
