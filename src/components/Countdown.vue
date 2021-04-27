<template>
  <div class="main-countdown-container">
    <transition name="fade">
      <div class="grid-container" v-if="!countdownFinished">
        <p class="heading days-heading">{{ $t("days") }}</p>
        <p class="heading hours-heading">{{ $t("hours") }}</p>
        <p class="heading mins-heading">{{ $t("minutes") }}</p>
        <div class="container day-counter">
          <div class="single-char">{{ this.days[0] }}</div>
          <div class="single-char">{{ this.days[1] }}</div>
        </div>
        <div class="container hour-counter">
          <div class="single-char">{{ this.hours[0] }}</div>
          <div class="single-char">{{ this.hours[1] }}</div>
        </div>

        <div class="container min-counter">
          <div class="single-char">{{ this.minutes[0] }}</div>
          <div class="single-char">{{ this.minutes[1] }}</div>
        </div>
      </div>
      <!-- <div class="count-numbers"></div> -->
    </transition>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      //   target_date: new Date(2021, 4, 9, 20, 0),
      target_date: new Date(2021, 3, 27, 16, 39),
      days: "00",
      hours: "00",
      minutes: "00",
      seconds: "00",
      changed: false,
      countdownFinished: false,
    };
  },
  mounted: function () {
    const itteration = window.setInterval(() => {
      console.log("RUnning");
      if (
        this.changed &&
        this.days === "00" &&
        this.hours === "00" &&
        this.minutes === "00" &&
        this.seconds === 0
      ) {
        clearInterval(itteration);
        this.countdownFinished = true;
      } else {
        this.changed = true;
        this.calcDifferenceRemaining();
      }
    }, 1000);
  },
  methods: {
    calcDifferenceRemaining: function () {
      let date_future = this.target_date;

      let date_now = new Date();

      let seconds = Math.floor((date_future - date_now) / 1000);
      let minutes = Math.floor(seconds / 60);
      hours = Math.floor(minutes / 60);
      let days = Math.floor(hours / 24);

      let hours = hours - days * 24;
      minutes = minutes - days * 24 * 60 - hours * 60;
      seconds = seconds - days * 24 * 60 * 60 - hours * 60 * 60 - minutes * 60;
      if (days < 10) {
        days = `0${days}`;
      } else {
        days = `${days}`;
      }

      if (minutes < 10) {
        minutes = `0${minutes}`;
      } else {
        minutes = `${minutes}`;
      }

      if (hours < 10) {
        hours = `0${hours}`;
      } else {
        hours = `${hours}`;
      }

      this.days = days;
      this.hours = hours;
      this.minutes = minutes;
      this.seconds = seconds;
    },
  },
  computed: {
    daysRemaining: function () {
      let Difference_In_Time = this.target_date.getTime() - this.now.getTime();

      // To calculate the no. of days between two dates
      let Difference_In_Days = Difference_In_Time / (1000 * 3600 * 24);
      return Math.round(Difference_In_Days);
    },
  },
};
</script>

<style scoped lang="scss">
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}

.home {
  background-color: gray;
}
.main-countdown-container {
  //   width: 50%;
  margin: auto;
  max-width: 1000px;
  text-align: center;
  padding: 20px 0;
  .grid-container {
    display: grid;
    grid-template-columns: 20% 20% 20%;
    justify-content: center;
    row-gap: 16px;
    column-gap: 1.5em;

    .heading {
      color: var(--light-white);
      margin-bottom: 0;
    }
    .container {
      display: flex;
      justify-content: center;
      justify-content: space-evenly;
      font-size: 85px;
      line-height: 1;

      .single-char {
        background-color: black;
        padding: 3px;
        border-radius: 8px;
        width: 60px;
        height: 60px;
        font-size: 55px;
        margin: 0 10px;
      }
    }
  }
}

@media screen and (max-width: 800px) {
  .grid-container {
    column-gap: 2em !important;

    .single-char {
      width: 45px !important;
      min-width: 45px;
      height: 45px !important;
      min-height: 45px;
      font-size: 40px !important;
      margin: 0 10px;
    }
  }
}

@media screen and (max-width: 600px) {
  .grid-container {
    column-gap: 3em !important;

    .single-char {
      width: 45px !important;
      min-width: 45px;
      height: 45px !important;
      min-height: 45px;
      font-size: 40px !important;
      margin: 0 5px !important;
    }
  }
}

@media screen and (max-width: 466px) {
  .main-countdown-container {
    padding-top: 22px;
  }
}

@media screen and (max-width: 450px) {
  .grid-container {
    column-gap: 4em !important;
    padding: 0 30px;
    .single-char {
      width: 45px !important;
      min-width: 45px;
      height: 45px !important;
      min-height: 45px;
      font-size: 40px !important;
    }
  }
}

@media screen and (max-width: 371px) {
  .grid-container {
    grid-template-columns: 100% !important;
    row-gap: 7px !important;
    .container {
      justify-content: center !important;
    }
    .day-counter {
      grid-column: 1;
      grid-row: 2;
    }
    .hour-counter {
      grid-column: 1;
      grid-row: 4;
    }
    .min-counter {
      grid-column: 1;
      grid-row: 6;
    }
    .days-heading {
      grid-column: 1;
      grid-row: 1;
    }
    .hours-heading {
      grid-column: 1;
      grid-row: 3;
    }
    .mins-heading {
      grid-column: 1;
      grid-row: 5;
    }
  }
}
</style>
