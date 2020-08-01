<template>
  <div>

    <app-slider></app-slider>

      <section class="skilld py-5" id="skills">
    <div class="container">
      <div class="row mb-5">
        <div class="col d-flex flex-wrap text-uppercase justify-content-center">
          <h1 class="font-weight-bold align-self-center mx-1">why choose</h1>
          <h1 class="section-title-special mx-1">Us</h1>
        </div>
      </div>
      <div class="row">
        <!--single skill-->
        <div class="col-sm-6 col-lg-3 text-center my-3">
          <a href="#" class="skills-icon p-2 rounded-circle">
            <i class="fas fa-people-carry fa-fw"></i>
          </a>
          <h6 class="text-uppercase font-weight-bold my-3">
            Lorem ipsum
          </h6>
          <div class="skills-underline"></div>
          <p class="w-75 mx-auto text-muted">Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi, totam.</p>
        </div>
        <!--end single skill-->
        <!--single skill-->
        <div class="col-sm-6 col-lg-3 text-center my-3">
          <a href="#" class="skills-icon p-2 rounded-circle">
            <i class="fas fa-comments fa-fw"></i>
          </a>
          <h6 class="text-uppercase font-weight-bold my-3">
            Lorem ipsum </h6>
          <div class="skills-underline"></div>
          <p class="w-75 mx-auto text-muted">Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi, totam.</p>
        </div>
        <!--end single skill-->
        <!--single skill-->
        <div class="col-sm-6 col-lg-3 text-center my-3">
          <a href="#" class="skills-icon p-2 rounded-circle">
            <i class="fas fa-people-carry fa-fw"></i>
          </a>
          <h6 class="text-uppercase font-weight-bold my-3">
            Lorem ipsum
          </h6>
          <div class="skills-underline"></div>
          <p class="w-75 mx-auto text-muted">Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi, totam.</p>
        </div>
        <!--end single skill-->
        <!--single skill-->
        <div class="col-sm-6 col-lg-3 text-center my-3">
          <a href="#" class="skills-icon p-2 rounded-circle">
            <i class="fas fa-wallet fa-fw"></i>
          </a>
          <h6 class="text-uppercase font-weight-bold my-3">
            Lorem ipsum
          </h6>
          <div class="skills-underline"></div>
          <p class="w-75 mx-auto text-muted">Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi, totam.</p>
        </div>
        <!--end single skill-->
      </div>
    </div>
  </section>

          <most-sell></most-sell>



                      <div class="section question py-5" id="question">
    <div class="container">
      <div class="row">
        <!-- single question first -->
        <div class="col-10 mx-auto my-2 col-md-6 d-flex justify-content-between
        question-gray p-4">
          <a href="#" class="question-icon mr-3">
            <i class="fas fa-search fa-fw"></i>
          </a>
          <div class="question-text w-75">
            <h4 class="question-title text-capitalize font-weight-bold">
              Lorem ipsum dolor sit amet?
            </h4>
            <p class="question-info">
              Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ullam, quis!</p>
          </div>
        </div>
        <!-- single question socond -->
        <div class="col-10 mx-auto my-2 col-md-6 d-flex justify-content-between
        question-blue p-4">
          <a href="#" class="question-icon mr-3">
            <i class="fas fa-dollar-sign fa-fw"></i>
          </a>
          <div class="question-text w-75">
            <h4 class="question-title text-capitalize font-weight-bold">
              Lorem ipsum dolor sit amet?
            </h4>
            <p class="question-info">
              Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ullam, quis!</p>
          </div>
        </div>
      </div>
    </div>
  </div>


  
          <latest-products></latest-products>

  </div>
</template>

<script>
import AppSlider from "./Components/Slider";
import MostSellProducts from "./Components/MostSellProducts";
import LatestProducts from "./Components/LatestProducts";
export default {
  components: {
    appSlider: AppSlider,
    mostSell: MostSellProducts,
    latestProducts: LatestProducts
  }
};
</script>
