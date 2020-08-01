<template>
            <div class="site-section block-3 site-blocks-2 bg-light">
            <div class="container">
                <div class="row justify-content-center">
                    <div class="col-md-7 site-section-heading text-center pt-4">
                        <h2>All Products</h2>
                    </div>
                </div>
                <div class="row">
              <div class="col-md-6 col-lg-3 ftco-animate" 
              v-for="product in FilterProducts.products"
              :key="product.productId">
                <div class="product">
                    <a href="#" class="img-prod">
                      <router-link :to="{name:'SingleProduct',params:{id:product.productId}}">
                        <img :src="ProductImageAddress+product.productImageName" width="253" height="202">
                      </router-link>
                    </a>
                    <div class="text py-3 pb-4 px-3 text-center">
                      <div class="block-4-text p-4">
                        <h3><a href="#">{{ product.productName.substring(0,30) }}</a></h3>
                        <p class="mb-0">{{product.description}}</p>
                        <p class="text-primary font-weight-bold">{{ product.price }}</p>
                      </div>
                    </div>
                </div>
              </div>
                </div>
            </div>
        </div>
</template>

<script>
export default {
  computed: {
    FilterProducts() {
      return this.$store.getters.GetProducts;
    },
    ProductImageAddress() {
      return this.$store.getters.GetProductImageAddress;
    }
  },
  watch: {
    $route() {
      this.$store.dispatch("GetProductsFromServer", {
        pageId: this.$route.query.pageId
      });
    }
  },
  created() {
    this.$store.dispatch("GetProductsFromServer", {
      pageId: 1
    });
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
