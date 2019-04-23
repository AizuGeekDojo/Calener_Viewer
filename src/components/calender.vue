<template>
  <div>
    <iframe
      src="https://calendar.google.com/calendar/embed?mode=WEEK&amp;height=600&amp;wkst=1&amp;bgcolor=%23FFFFFF&amp;src=646mrbqs7kg1g7869hatdlan6o%40group.calendar.google.com&amp;color=%23B1365F&amp;ctz=Asia%2FTokyo"
      style="border-width:0"
      width="800"
      height="600"
      frameborder="0"
      scrolling="no"
    ></iframe>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      intervalId: undefined
    };
  },
  mounted() {
    this.intervalId = setInterval(function() {
      this.route.push("/");
    }, 86400000);
  },
  beforeDestroy() {
    console.log("clearInterval");
    clearInterval(this.intervalId);
  }
};
</script>
