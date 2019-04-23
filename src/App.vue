<template>
  <div id="app">
    <router-view class="daytime_display" v-if="is_daytime" />
    <div class="not_daytime_display" v-if="!is_daytime"></div>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      is_daytime: true,
      intervalid: undefined
    };
  },
  mounted() {
    this.intervalId = setInterval(() => {
      this.check_daytime();
    }, 1000 * 60 * 60);
    this.check_daytime();
  },
  beforeDestroy() {
    console.log("clearInterval");
    clearInterval(this.intervalId);
  },
  methods: {
    check_daytime() {
      let now_hour = new Date().getSeconds();
      if (now_hour > 18 || now_hour < 7) {
        this.is_daytime = false;
      } else {
        this.is_daytime = true;
      }
    }
  }
};
</script>

<style>
html {
  width: 100%;
  height: 100%;
  margin: 0 auto;
}
body {
  width: 100%;
  height: 100%;
  margin: 0 auto;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100%;
  height: 100%;
  margin: 0 auto;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.not_daytime_display {
  background-color: black;
  width: 100%;
  height: 100%;
  margin: 0 auto;
}

.daytime_display {
  margin-top: 50px;
}
</style>
