# stemjar
</div>
    <div class="ml-auto">
      <ul class="navbar-nav mr-auto ml-5 align-items-center">
        <li class="nav-item">
          <router-link
            to="/search"
            type="toggle button"
            class="btn mr-2 btn-outline-light"
            id="add-btn"
          >
            <i class="search"></i>
            Search
          </router-link>
        </li>
        <li v-if="$store.state.isAdmin" class="nav-item">
          <router-link
            to="/admin/done"
<div class="text" style="width: rem;">
    <div class="checkbox">
      <button @click="done(product)" class="btn btn-checkbox-btn">
      <button v-if="product && product.stock > 0" @click="done(product)" class="btn done-btn">
        <i v-if="!hasdone(product && product._id)" class="fal fa-cart-arrow-down"></i>
        <p v-else class="lead mb-0">In Cart</p>
      </button>
      <button disabled v-else class="btn btn-danger cart-btn">
        <p class="lead mb-0">Out of Stock</p>
      </button>
    </div>
    <div class="text-body  border-top">
      <div class="d-flex justify-content-between align-items-center">
</div>
    <app-not-found v-else-if="!product" />
    <div v-else-if="product">
        <h2 class="text-center text-danger mb">{{ product.model }}</h2>
        <h2 class="text-center text-info mb">{{ product.dish }}</h2>
        <div class="row">
            <div class="col-xl col-md text-center">
            <div class="col-xl col-md text-center">
                <div class="name">
                </div>
            </div>
            <div class="col-xl col-md">
                <h3 class="text-muted">Model: <span class="text-dark">{{ product.model }}</span></h3>
                <h5 class="text-muted">
                    Made By
                    <span class="text-dark">{{ product.brand }}</span>
            <div class="col-xl-7 col-md-12 m-auto">
                <h4 class="mb-1 font-weight-bold text-center" :class="[ {'text-success': product.stock > 0}, {'text-danger': product.stock <= 0} ]">
                    {{ product.stock > 0 ? 'In Stock' : 'Out of Stock' }}
                </h4>
                <h5 class="text-info">
                    Dish offered from:
                    <span class="text-dark font-weight-bold">{{ product}}</span>
                </h5>
                <h5 class="text-primary">
                    <span class="text-muted">Price:</span>
                    ₹ {{ formatPrice(product.price) }}
                <h5 class="text-info">
                    Price:
                    <span class="text-dark font-weight-bold">₹ {{ formatPrice(product.price) }}</span>
                </h5>

                <h5 class="text-muted">
                <h5 class="text-info">
                    Average Rating: 
                    <!--- Star Ratings  --->
                    <div class="reviews stars-outer ml-1">
                        <div class="stars-inner" :style="{'width': `${(product.averageRating/5)*100}%`}"></div>
                    </div>
                </h5>
                <h6 class="text-danger border-bottom border-dark">
                    Some info about the Product
                <h6 class="text-info border-bottom border-dark">
                    Dish Descriptions
                </h6>
                <p class="text-dark">{{ product.description }}</p>
                <router-link to="/" class="btn btn-outline-primary btn-sm mr-3">
                    <p class="mb-0">Back to today's menu</p>
                </router-link>
                <button @click="done(product)" class="btn btn-sm btn-outline-warning">
                    <i v-if="!hasCarted(product._id)" class="fa-2x fal fa-cart-arrow-down"></i>
                    <p v-else class="mb-0">In Cart</p>
                <button :disabled='product.stock <= 0'  @click="done(product)" class="btn" :class="[{'btn-outline-warning': product.stock > 0}, {'btn-danger': product.stock <= 0}]">
                    <span v-if="!hasdone(product._id) && product.stock > 0">done<i  class="fal fa-cart-arrow-down"></i></span>
                    <span v-else-if="product.stock <= 0">Out of Stock</span>
                    <span v-else class="mb-0">In Cart</span>
                </button>
                <div class="container mt-2 review-container">
                            {{show_reviews ? 'Hide Reviews' : 'Show Customer Reviews'}}
                        </a>
                    </div>
                    <div v-if="show_reviews">
                </div>
            </div>
        </div>
        <div class="container px-5 mt-4">
            <div v-if="show_reviews">
                      <div id='add-review-form' class="card bg-light p-4 mb-3">
                        <h3 class="text-dark">Add a Review:</h3>
                        <form @submit.prevent="processReview()
                    </div>
                    <app-product-reviews :productID="this.$route.params.id" />
                  </div>
                </div>
            </div>
        </div>
    </div>
</div> export default {
    },
    async mounted() {
        await this.$store.dispatch("fetchSingleProduct", this.$route.params.id);
        if(this.$route.hash && this.$route.hash.split("#")[1] === 'feedback') {
            this.show_reviews = true;
        }
    },
    methods: {
        ...mapActions(["done"]), export default {
}
img {
.image img {
    height: 100%;
    width: 100%;
}
h2, h6 {
.btn {
    box-shadow: none !important;
}
 2  client/src/components/pages/Products.vue 
<template>
  <div class="container mt-3">
    <h1 class="text-center mb-5 font-weight-bold">items</h1>
    <h1 class="text-center mb-4 font-weight-bold">items</h1>
    <div v-if="loading" class="container text-center">
      <img src="@/assets/search.gif" alt="Loader" />
    </div>
  8  client/src/components/pages/adminOrders.vue 

    </div>
    <div v-else>
      <h1 v-if="isEmpty" class="text-center order-empty-text mt-5">
        Phone Store don't have any order yet
        Food Site don't have any order yet
      </h1>
      <div v-else class="mt-3">
        <div>
            <table class="table products-table mt-4">
              <thead>
                <tr class="text-uppercase">
                  <th scope="col">products</th>
                  <th scope="col">model</th>
                  <th scope="col">food items</th>
                  <th scope="col">dish</th>
                  <th scope="col">price</th>
                  <th scope="col">quantity</th>
                </tr>
                  </th>
                  <td>
                    <router-link :to="'/view/' + item.product._id">{{
                      item.product.model
                      item.product.dish
                    }}</router-link>
                  </td>
                  <td class="price">₹ {{ formatPrice(item.product.price) }}</td>
    client/src/components/pages/cart.vue 
              <router-link :to="'/view/' + item._id">{{
                item.dish
              }}</router-link>
              <br>
              <p v-if="item.stock <= 0" class='lead text-danger'>Out of Stock</p>
            </td>
            <td class="price">₹ {{ formatPrice(item.price) }}</td>

                  -
                </button>
                <button type="button" class="btn btn-outline-info">
                  {{ item.quantity }}
                  {{ item.quantity > item.stock ? item.stock : item.quantity }}
                </button>
                <button
                  @click="changeQuantity(item._id, 1)"
                  :disabled="item.quantity > 9"
                  :disabled="item.stock===1 || item.stock < item.quantity"
                  type="button"
                  class="btn btn-outline-info"
               
            >₹ {{ formatPrice((taxTotal + productTotal).toFixed(2)) }}</span
          >
        </p>
        <button @click="checkout" class="btn mt-1 mb-4 btn-success">
          Proceed to Checkout
        <button :disabled="availibilityChecking" @click="checkout" class="btn mt-1 mb-4 btn-success">
          {{!availibilityChecking ? 'Proceed to Checkout' : 'Checking Availibility'}}
          <i class="ml-1 fal fa-shopping-cart"></i>
        </button>
      </div>
 export default {
      showSaveButton: false,
      loading: false,
      cartSaved: null,
      availibilityChecking: false,
    };
  },
  watch;
export default {
    // TODO only for Development
    async checkout() {
      try {
        this.availibilityChecking = true;
        if (this.isChanged) {
          await this.handleSaveCart();
        }
        this.$router.push("/checkout/shipping");
        
        const available = await this.$store.dispatch("checkAvailivility");
        this.availibilityChecking = false;
        
        if(available) {
          this.$router.push("/checkout/shipping");
        }
        
      } catch (error) {
        console.error(error);
      }
   client/src/components/pages/search.vue 

<template>
  <div class="container">
      <div class="jumbotron py-2 bg-light">
          <h1 class="align-left">
              todays menu
          </h1>
        <form @submit.prevent="handleSearching">
        <div class="input-group mb-3">
            <div class="input-group-prepend">
                <span class="input-group-text" id="inputGroup-sizing-default">
                    <i class="fal fa-search"></i>
                </span>
            </div>
            <input required v-model="text" type="text" placeholder='Serach Food Items ... ( By Dish Name )' class="form-control" aria-label="Default" aria-describedby="inputGroup-sizing-default">
        </div>
        <div class="row">
            <div class="col-md-6">
                <p class="lead text-info">
                    Apply Filters <i class="fad fa-filter"></i>
                </p>
            </div>
            <div class="col-md-6">
                <p @click="clearFilters" class="lead text-danger ml-auto clear-fliter">
                    Clear Filters <i class="ml-2 fal fa-times"></i>
                </p>
            </div>
        </div>

        <div class="form-row">
            <div class="form-group col-md-4">
                <label>Selct Category</label>
                <select required class="form-control" v-model="category">
                    <option disabled>Choose ...</option>
                    <option v-for="it in foodCategories" :key='it'>{{ it }}</option>
                </select>
            </div>
            <div class="form-group col-md-4">
                <label>Price Range</label>
                <div class="input-group mb-2 mr-sm-2">
                    <div class="input-group-prepend">
                    <div class="input-group-text">Upto Rs.</div>
                    </div>
                    <input
                        v-model="price"
                        required
                        type="number"
                        min="1"
                        class="form-control"
                        placeholder="100"
                    />
                </div>
            </div>
        </div>
        <div class="form-row">
            <div class="form-group col-md-5">
                <div class="custom-control custom-switch">
                    <label class="form-check-label">
                        <input v-model="stockedItems" class="form-check-input" type="checkbox">
                        Show only Stocked in Food Items
                    </label>
                </div>
            </div>
            <div class="form-group col-md-4">
                <button class="btn btn-success px-2"><i class="fal fa-file-search"></i> {{ searching ? 'Serching ...' : 'Search' }}</button>
            </div>
        </div>
        </form>
      </div>
        <div class='row' v-if="searching">
            <img src="@/assets/search.gif" alt="" class="mx-auto" />
        </div>
      <div v-else-if="!initialState">
          <h2 class="text-center mb-1 text-info font-weight-bold">Serach Results</h2>
          <p v-if='results && results.mathedFound > 0' class='text-center text-muted mb-3 lead'>{{ results && results.mathedFound }} Results found</p>
          <div class="row mb-3">
            <h3 v-if="results && results.mathedFound === 0" class="mx-auto order-empty-text">
                No matching foods found
            </h3>
                <div
                    v-for="item in results.results"
                    :key="item._id"
                >
                    <app-product-item :product="item" />
                </div>
            </div>
      </div>
  </div>
</template>

<script>
import ProductItem from "../layouts/ProductItem";
export default {
    name: "Serach-Foods",
    components: {
        "app-product-item": ProductItem,
    },
    computed: {
        results() {
            return this.$store.state.searchResults;
        },
    },
    data() {
        return {
            searching: false,
            text: "",
            category: "Choose ...",
            price: 100,
            stockedItems: true,
            foodCategories: [
                 chicken curry
		 egg curry
		 bhindi fry
                ],
            initialState: true,
        }
    },
    methods: {
        checkToggleButton() {
            this.stockedItems = !this.stockedItems;
        },
        clearFilters() {
            this.stockedItems = false;
            this.price = 100;
            this.category = "Choose ...";
        },
        async handleSearching() {
            this.searching = true;
            if(this.text.trim().length === 0) {
                return;
            }
            let query = `text=${this.text}`
            if(this.category !== 'Choose ...') {
                query += `&category=${this.category}`;
            }
            }
            query += `&price=${this.price}`;
            query += `&stocked=${this.stockedItems}`;
            await this.$store.dispatch('fecthSearchResults', query)
            this.searching = false;
            this.initialState = false;
        }
    }
}
</script>

                  </div>
                </th>
                <td>
                  <router-link :to="'/view/' + item.product._id">{{
                    item.product.dish
                  }}</router-link>
                  {{item.product.dish}}
                  <br>
                  <router-link :to="'/view/' + item.product._id + '#feedback'">Give Feedback</router-link>
                </td>
                <td class="price">₹ {{ formatPrice(item.product.price) }}</td>
 2  client/src/components/utils/BackDrop.vue 
<template>
  <div v-if="loading" class="container d-flex justify-content-center align-items-center">
    <div class="modal-box text-center">
      <h5 class="font-weight-normal">Product Details is Uploading ...</h5>
      <h5 class="font-weight-normal">New Dish is Uploading ...</h5>
      <img class="my-3" src="@/assets/backdrop.gif" alt />
    </div>
  </div>
  5  client/src/routes/routes.js 
	const routes = [{
				name: 'User-Orders',
				component: () => import('@/components/pages/userOrder.vue'),
			},
			{
				path: '/search',
				name: 'Search-Foods',
				component: () => import('@/components/pages/search.vue'),
			},


			// Admin Routes
 107  client/src/store/actions/admin/addProduct.js 
import axios from "axios";
import createConfig from '../../helpers/api-auth';
import path from "path";
import firebase from "@/firebase";
import crypto from "crypto";


export default {
    async addAdminProducts(context, product) {
      try {
        context.commit("SET_PRODUCT_UPLOADING", true);
        const photoURL = await context.dispatch(
          "fileUploadToStorage",
          product.file
        );
        const dbProduct = {
          ...product.info,
          photoURL,
        };
        const res = await axios.post(
          "/api/v1/admin/add-product",
          dbProduct,
          createConfig()
        );
        context.commit("ADD_PRODUCT_IN_LIST", dbProduct);
        context.commit("SET_PRODUCT_UPLOADING", false);
        context.commit("SET_ERRORS", res.data);
      } catch (e) {
        console.log(e);
      }
    },


    async fileUploadToStorage(context, file) {
      try {
        const storage = firebase.storage();
        const extName = path.extname(file.name);
        const fileOnlyName = crypto
          .randomBytes(15)
          .toString("hex")
          .toUpperCase();
        const storageRef = storage.ref(`uploads/${fileOnlyName}${extName}`);
        const metadata = {
          contentType: `${file.type}`,
        };
        await storageRef.put(file, metadata);
        const downloadURL = await storageRef.getDownloadURL();
        return downloadURL;
      } catch (e) {
        console.log(e);
      }
    },

import axios from "axios";
import createConfig from '../../helpers/api-auth';
import path from "path";
import firebase from "@/firebase";
import crypto from "crypto";


export default {
    async addAdminProducts(context, product) {
      try {
        context.commit("SET_PRODUCT_UPLOADING", true);
          "fileUploadToStorage",
          product.file
        );
        const dbProduct = {
          ...product.info,
          photoURL,
        };
        const res = await axios.post(
          "/api/v1/admin/add-product",
          dbProduct,
          createConfig()
        );
        dbProduct._id = res.data.id;
        context.commit("ADD_PRODUCT_IN_LIST", dbProduct);
        context.commit("SET_PRODUCT_UPLOADING", false);
        context.commit("SET_ERRORS", res.data);
      } catch (e) {
        console.log(e);
      }
    },


    async fileUploadToStorage(context, file) {
      try {
        const storage = firebase.storage();
        const extName = path.extname(file.name);
        const fileOnlyName = crypto
          .randomBytes(15)
          .toString("hex")
          .toUpperCase();
        const storageRef = storage.ref(`uploads/${fileOnlyName}${extName}`);
        const metadata = {
          contentType: `${file.type}`,
        };
        await storageRef.put(file, metadata);
        const downloadURL = await storageRef.getDownloadURL();
        return downloadURL;
      } catch (e) {
        console.log(e);
      }
    },

} 
  client/src/store/actions/cart.js 

import axios from "axios";
import createConfig from '../helpers/api-auth';
// import firebase from "@/firebase";
// import path from "path";


export default {

    async addToCart(context, product) {
      try {
        const hasAlready = context.state.cart.find(
          (item) => item._id === product._id
        );
        if (!hasAlready) {
          context.commit("ADD_TO_CART", product);
          await context.dispatch("saveCartProduct");
          context.commit("CART_NOTIFICATION", product);
        }
      } catch (e) {
        console.log(e);
      }
    },

    async saveCartProduct(context) {
      try {
        await axios.post(
          "/api/v1/save-cart", {
            cart: context.state.cart.map(item => {
              return {
                product: item._id,
                quantity: item.quantity,
              }
            }),
          },
          createConfig()
        );
      } catch (e) {
        console.log(e);
      }
    },
import axios from "axios";
import createConfig from '../helpers/api-auth';
// import firebase from "@/firebase";
// import path from "path";


export default {

    async addToCart(context, product) {
      try {
        const hasAlready = context.state.cart.find(
          (item) => item._id === product._id
        );
        if (!hasAlready) {
          context.commit("ADD_TO_CART", product);
          await context.dispatch("saveCartProduct");
          context.commit("CART_NOTIFICATION", product);
        }
      } catch (e) {
        console.log(e);
      }
    },

    async saveCartProduct(context) {
      try {
        await axios.post(
          "/api/v1/save-cart", {
            cart: context.state.cart.map(item => {
              return {
                product: item._id,
                quantity: item.quantity,
              }
            }),
          },
          createConfig()
        );
      } catch (e) {
        console.log(e);
      }
    },

    async checkAvailivility(context) {
      try {
        const res = await axios.get('/api/v1/check-stock', createConfig());
        if(res.data.code === 400) {
            context.commit("SET_ERRORS", {
            code: "Notification",
            message: res.data.msg,
          });
          context.commit("SET_CART_STATE", res.data.cart);
          return false;
        } else return true;
      } catch (error) {
        console.log(error);
      }
    }
