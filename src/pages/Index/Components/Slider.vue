<template>
  <header class="header" id="header">
    <div class="container-fluid">
      <div class="row height-max align-items-center">
        <div class="col-md-9 ml-auto text-right pr-5">
          <h5 class="title-heading d-inline-block p-2 text-uppercase">the all new</h5>
          <h2 class="text-uppercase my-2 title">2020 fashion trend</h2>
          <h3 class="text-uppercase">Online Closet</h3>
          <h6 class="text-capitalize">be cheel</h6>
        </div>
      </div>
    </div>
  </header>


</template>

<script>
export default {
  computed: {
    Sliders() {
      return this.$store.getters.GetSliders;
    },
    SliderImageAddress() {
      return this.$store.getters.GetSliderImageAddress;
    }
  },
  created() {
    if(this.Sliders.length == 0){
      this.$store.dispatch("GetSlidersFromServer");
    }
  }
};
</script>

