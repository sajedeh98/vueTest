<template>
  <section class="inventory py-5" id="inventory">
    <div class="container">

      <div class="row mb-5">
        <div class="col d-flex flex-wrap text-uppercase justify-content-center">
          <h1 class="font-weight-bold align-self-center mx-1">Latest</h1>
          <h1 class="section-title-special mx-1">Products</h1>
        </div>
      </div>


      <div class="row">
        <!--Single Car-->
        <div class="col-10 mx-auto my-3 col-md-6 col-lg-4" v-for="product in LatestProducts" :key="product.productId">
          <div class="card car-card">
              <router-link :to="{name:'SingleProduct',params:{id:product.productId}}">
                <img :src="ProductImageAddress+product.productImageName" class="card-img-top car-img">
              </router-link>
            <div class="card-body">
              <div class="car-info d-flex justify-content-between">
                <div class="car-text text-uppercase">
                  <h6 class="font-weight-bold">{{ product.productName.substring(0,30) }}</h6>
                </div>
                <h5 class="car-value align-self-center py-2 px-3">
                  <span class="car-price">{{ product.price }}</span>
                </h5>
              </div>
            </div>
            <!--footer-->
            <div class="card-footer text-capitalize d-flex justify-content-between">
              <router-link :to="{name:'SingleProduct',params:{id:product.productId}}">
                <span style="padding-left: 100px;">Add To Shop</span>
              </router-link>
              
            </div>
          </div>
        </div>
        <!--End Single Car-->
      </div>
    </div>

  </section>

</template>
<script>
export default {
  computed: {
    LatestProducts() {
      return this.$store.getters.GetLatestProducts;
    },
    ProductImageAddress() {
      return this.$store.getters.GetProductImageAddress;
    }
  },
  created() {
    if(this.LatestProducts.length == 0){
      this.$store.dispatch("GetLatestProductsFromServer");
    }
  },
    methods: {
    AddProductToOrder(productId) {
      const orderDetail = {
        productId: productId,
        count: 1
      };

      this.$store.dispatch("AddProductToOrder", orderDetail);
    }
  }
};
</script>
