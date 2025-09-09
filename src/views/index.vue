<template>
  <div>
    <el-carousel height="400px">
      <el-carousel-item v-for="image in images" :key="image.id">
        <el-image style="width: 100%" :src="image.url" fit="cover" />
      </el-carousel-item>
    </el-carousel>
  </div>
</template>

<script>
export default {
  data() {
    return {
      swiperOption: {
        autoplay: {
          delay: 1500,
        },
        slidesPerView: "auto",
        centeredSlides: true,
        spaceBetween: 30,
        loop: true,
        activeIndex: 2,
      },

      images: [
        { url: "src/assets/images/banner1.png" },
        { url: "src/assets/images/banner2.png" },
        { url: "src/assets/images/banner3.png" },
      ],
      bidData1: undefined,
      bidData2: undefined,

      searchDialogOpenState: false,
      keyword: "",
      searchResult: [],
    };
  },
  methods: {
    jumpTo(id) {
      this.$router.push(`/bid/detail?id=${id}`);
    },
  },
  mounted() {},
};
</script>

<style scoped>
.swiper {
  height: 33vh;
}

.swiper-wrapper {
  width: 100vw;
}

.swiper-slide {
  width: 1000px;
  /* margin-left: 30px; */
}

.bannerImage {
  width: 100%;
  height: 35vh;
  border-radius: 10px;
  opacity: 1;
  border: 0;
}

.card-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-gap: 50px;
  padding: 0 calc((100% - 1250px) / 2);
  margin-top: 50px;
}

@media screen and (max-width: 540px) {
  .card-container {
    width: 100%;
    padding: 0;
    grid-template-columns: 1fr;
  }
}

.item:hover {
  color: #1ad0b6;
}
</style>
