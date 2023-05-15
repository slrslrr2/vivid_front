<template>
  <div class="flex">
    <div
      class="flex flex-col w-full lg:w-[395px] p-[25px] bg-white dark:bg-[#364680] rounded-[20px] mt-[18px] xl:ml-[18px]"
    >
      <!-- Title -->
      <div class="flex justify-between">
        <h3 class="text-[18px] text-[#363E64] dark:text-white">인기검색어</h3>

        <i class="ri-search-line text-[22px] text-[#C3C8DE]"></i>
      </div>

      <!-- locations -->
      <div v-if="popularSearchWords.length > 0" class="flex flex-row">
        <div
          class="flex mr-2 flex-wrap w-full bg-[#FFF8F0] dark:bg-[#00000026] rounded-2xl px-[15px] py-5 mt-5"
        >
          <button
            v-for="(item, index) in popularSearchWords"
            :key="index"
            class="pl-2 pr-2 mr-2 flex justify-center mb-2 items-center h-[35px] rounded-md bg-[#F5F8FF] dark:bg-[#1E3364] text-[#5C92FF] transition ease-in-out duration-300 hover:cursor-pointer hover:bg-[#E2EAFC] dark:hover:bg-[#001c5c]"
          >
            {{ item.key }}
          </button>
        </div>
      </div>

      <div v-else class="flex flex-row h-full">
        <div
          class="flex mr-2 h-full flex-col w-full bg-[#FFF8F0] dark:bg-[#00000026] rounded-2xl px-[15px] py-5 mt-5 flex items-center justify-center"
        >
          <p class="text-[14px] md:text-[16px] font-medium text-[#5C92FF]">
            등록된 데이터가 없습니다
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      popularSearchWords: [],
    };
  },
  created() {
    this.getPopularSearchWords();
  },
  methods: {
    async getPopularSearchWords() {
      const { data } = await this.$axios.get(
        `/api/search/popular/search/word/list`
      );
      this.popularSearchWords.push(...data);
    },
  },
};
</script>

<style></style>
