<template>
  <div class="main-countdown-container">
    <div class="grid-container">
      <p class="heading">Days</p>
      <p class="heading">Hours</p>
      <p class="heading">Minutes</p>
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
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      target_date: new Date(2021, 4, 9, 20, 0),
      days: "00",
      hours: "00",
      minutes: "00",
      seconds: "00",
    };
  },
  mounted: function () {
    window.setInterval(() => {
      console.log("RUnning");
      this.calcDifferenceRemaining();
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
.home {
  background-color: gray;
}
.main-countdown-container {
  width: 50%;
  margin: auto;
  text-align: center;
  .grid-container {
    display: grid;
    grid-template-columns: 20% 20% 20%;
    justify-content: center;
    row-gap: 16px;
    column-gap: 20px;

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
      }
    }
  }
}

@media screen and (max-width: 1600px) {
  .main-countdown-container {
    width: 65%;
  }
}

@media screen and (max-width: 1600px) {
  .main-countdown-container {
    width: 80%;
    .container {
      font-size: 60px !important;

      .single-char {
        width: 40px;
      }
    }
  }
}

@media screen and (max-width: 900px) {
  .main-countdown-container {
    width: 100%;

    .container {
      font-size: 40px !important;

      .single-char {
        width: 30px !important;
        margin: 5px !important;
      }
    }
  }
}
</style>
