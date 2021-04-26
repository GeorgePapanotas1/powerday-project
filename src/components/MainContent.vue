<template>
  <div class="main-content">
    <div class="inner_wrapper">
      <div class="content-wrapper">
        <img src="../../public/main_img.png" alt="" />
        <div class="text-big-items">
          <p class="left-text">Celebrating Choices</p>
          <p class="right-text">09.05 | 20:00</p>
        </div>

        <div class="hashes">
          <p>#LEBeauty</p>
          <p>#LRRecognitions</p>
          <p>#LREducation</p>
          <p>#LRGrowth</p>
          <p>#LRCars</p>
          <p>#LRSuccess</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
.main-content {
  margin-top: 15px;
  .inner_wrapper {
    width: 70%;
    margin: auto;

    .text-big-items {
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 78%;
      margin: auto;

      .left-text {
        font-size: 35px;
        line-height: 1.67;
        font-weight: 600;
      }
      .right-text {
        font-size: 35px;
        line-height: 1.67;
        font-weight: 400;
      }
    }
  }

  img {
    max-width: 1440px;
    min-width: 320px;
    width: 100%;
  }

  .hashes {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 65%;
    margin: auto;
  }
}
</style>
