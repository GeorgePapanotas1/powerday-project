<template>
  <div class="main-content">
    <div class="inner_wrapper">
      <div class="content-wrapper">
        <img src="../../public/main_img.png" alt="" />
        <div class="text-big-items">
          <p class="left-text">{{ $t("bottom_text") }}</p>
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
    margin: auto;
    max-width: 1440px;
    min-width: 200px;

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

@media screen and (max-width: 860px) {
  .text-big-items {
    width: 100% !important;
    flex-direction: column;

    .left-text {
      margin-bottom: 0 !important;
    }
    .right-text {
      margin-top: 0 !important;
    }
  }
}

@media screen and (max-width: 1000px) {
  .hashes {
    display: grid !important;
    grid-template-columns: 33% 33% 33%;
    text-align: center;
  }
}

@media screen and (max-width: 700px) {
  .hashes {
    width: 100% !important;
  }
}

@media screen and (max-width: 575px) {
  .content-wrapper {
    img {
      margin-top: 25px;
    }
    .text-big-items {
      margin-top: 30px !important;
      p {
        font-size: 25px !important;
      }
    }

    .hashes {
      margin-top: 30px !important;
      p {
        font-size: 13px;
      }
    }
  }
}

@media screen and (max-width: 425px) {
  .text-big-items {
    p.left-text {
      font-size: 24px !important;
    }
  }
}

@media screen and (max-width: 320px) {
  .text-big-items {
    p.left-text {
      font-size: 16px !important;
    }
  }
}
</style>
