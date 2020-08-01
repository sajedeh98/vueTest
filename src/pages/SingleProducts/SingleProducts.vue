<template>
      <!-- <section class="ftco-section">
    	<div class="container">
    		<div class="row">
    			<div class="col-lg-6 mb-5 ftco-animate">
    				<a href="pics/product-1.jpg" class="image-popup">
            <img :src="ProductImageAddress+SingleProduct.productImageName" class="img-fluid" alt="Colorlib Template"></a>
    			</div>
    			<div class="col-lg-6 product-details pl-md-5 ftco-animate">
    				<h3>{{SingleProduct.productName}}</h3>
    				<p class="price"><span>{{SingleProduct.price}}</span></p>
    				<p>
              {{SingleProduct.description}}
					</p>
						<div class="row mt-4">
							<div class="w-100"></div>
							<div class="input-group col-md-6 d-flex mb-3">
                  <label>Count</label>
	             	<input type="text" v-model="count" id="quantity" name="quantity" class="form-control input-number" value="1" min="1" max="100">
	          	</div>
	          	<div class="w-100"></div>
          	</div>
          	<button type="button" class="btn btn-fefault cart" @click="AddProductToOrder(SingleProduct.productId)">
              <i class="fa fa-shopping-cart"></i>
              Shop
            </button>
    			</div>
    		</div>
        <suggested-products></suggested-products>
    	</div>
    </section> -->


      <section>
    <div class="container">
      <div class="row">
        <div class="col-sm-12 padding-right">
          <div class="product-details">
            <!--product-details-->
            <div class="col-sm-7">
              <div class="view-product">
                <img :src="ProductImageAddress + SingleProduct.productImageName" />
              </div>
            </div>
            <div class="col-sm-5">
              <div class="product-information">
                <div>
                  <h2>{{ SingleProduct.productName }}</h2>
                </div>
                <div>
                  <span>
                    <p>{{ SingleProduct.description }}</p>
                    <span>{{ SingleProduct.price }} $</span>
                  </span>
                  <br /><br />
                  <span>
                    <label>count :</label>
                    <input type="text" class="search_box" v-model="count" />
                    <button type="button" class="btn btn-fefault cart block button-shop" @click="AddProductToOrder(SingleProduct.productId)">
                      <i class="fa fa-shopping-cart"></i>
                      افـزودن به سبـد خریـد
                    </button>
                  </span>
                </div>
                <div>
                  
                </div>
              </div>
            </div>
          </div>
          <suggested-products></suggested-products>
        </div>
      </div>
    </div>
  </section>




</template>

<script>
import SuggestedProducts from "./Components/SuggestedProducts";
export default {
  computed: {
    SingleProduct() {
      return this.$store.getters.GetSingleProduct;
    },
    ProductImageAddress() {
      return this.$store.getters.GetProductImageAddress;
    }
  },
  watch: {
    $route() {
      this.$store.dispatch("GetSingleProductFromServer", {
        productId: this.$route.params.id
      });
    }
  },
  components: {
    suggestedProducts: SuggestedProducts
  },
  created() {
    this.$store.dispatch("GetSingleProductFromServer", {
      productId: this.$route.params.id
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
  },
  data() {
    return {
      count:this.count
    }
  }
};
</script>
