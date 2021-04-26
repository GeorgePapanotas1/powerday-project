<template>
  <div id="app">
    <div id="nav">
      <div class="main-nav">
        <img src="../public/LRCMYK.png" alt="" />
        <img src="../public/PowerDayLogo.png" alt="" />
        <div class="lang-swicher">
          <router-link to="/">Gr</router-link> /
          <router-link to="/about">En</router-link>
        </div>
      </div>
      <div class="colored-boxes">
        <img src="../public/boxes.jpg" alt="" />
      </div>
    </div>
    <router-view />
  </div>
</template>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");

:root {
  --light-white: #fefefe;
  --light-gray: #8c8c8c;
}
body {
  margin: 0 !important;
}

#app {
  font-family: "Montserrat", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: black;
  color: var(--light-white);
  width: 100%;
}

#nav {
  padding-top: 35px;
  border-bottom: 1px solid var(--light-gray);
  .main-nav {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
  }

  .colored-boxes {
    text-align: center;
    margin-top: 30px;
    position: relative;
    img {
      width: 20% !important;
      position: relative;
      bottom: -4px;
    }
  }

  a {
    font-weight: normal;
    color: white;

    &.router-link-exact-active {
      font-weight: bold;
    }
  }
}
</style>
