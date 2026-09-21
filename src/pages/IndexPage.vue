<template>
  <div class="shop-page">
    <div class="top-area">
      <div class="top-links">
        <span>SAVE MORE ON APP</span>
        <span>BECOME A SELLER</span>
        <span>HELP & SUPPORT</span>
        <span>LOGIN</span>
        <span>SIGN UP</span>
        <span>ভাষা</span>
      </div>

      <div class="main-header">
        <div class="logo-icon">
          <q-icon name="shopping_cart" color="white" size="40px" />
        </div>

        <div class="brand-title">Daraz</div>

        <div class="search-area">
          <q-input
            v-model="search"
            bg-color="white"
            color="orange"
            placeholder="Search in Daraz"
            dense
            outlined
          >
            <template v-slot:append>
              <q-btn flat round color="orange" icon="search" />
            </template>
          </q-input>

          <div class="search-tags">
            dress for girls | watch for man | smart watch | t shirt | headphone
          </div>
        </div>

        <div class="cart-area">
          <q-icon name="shopping_cart" size="32px" />
        </div>
      </div>
    </div>

    <div class="category-area">
      <q-btn
        flat
        no-caps
        label="Categories"
        icon-right="keyboard_arrow_down"
        color="indigo-10"
      />
    </div>

    <div class="content-area">
      <div class="breadcrumb">
        Sports & Outdoors
        <q-icon name="chevron_right" />
        Shoes & Clothing
        <q-icon name="chevron_right" />
        Men
        <q-icon name="chevron_right" />
        Clothing
        <q-icon name="chevron_right" />
        Jerseys
        <q-icon name="chevron_right" />
        Football
      </div>

      <div class="product-layout">
        <div class="gallery-column">
          <q-card flat bordered class="gallery-card">
            <q-carousel
              v-model="slide"
              animated
              arrows
              navigation
              infinite
              swipeable
              height="430px"
              control-color="orange"
            >
              <q-carousel-slide
                v-for="(item, index) in images"
                :key="index"
                :name="index"
                class="image-slide"
              >
                <q-img
                  :src="item"
                  fit="contain"
                  class="full-width full-height"
                />
              </q-carousel-slide>
            </q-carousel>
          </q-card>

          <div class="thumbnail-list">
            <q-card
              v-for="(item, index) in images"
              :key="index"
              flat
              bordered
              class="thumbnail-card"
              :class="slide === index ? 'thumbnail-active' : ''"
              @click="slide = index"
            >
              <q-img :src="item" width="70px" height="70px" fit="cover" />
            </q-card>
          </div>
        </div>

        <div class="info-column">
          <q-card flat class="product-card">
            <q-card-section>
              <div class="product-title">
                Brazil World Cup Jersey 2026 Thai Premium Football Jersey For
                Men - Half Sleeve World Cup T Shirt - Brazil Jersey 2026
              </div>

              <div class="rating-line">
                <q-rating
                  :model-value="4.5"
                  max="5"
                  size="20px"
                  color="orange"
                  icon="star_border"
                  icon-selected="star"
                  icon-half="star_half"
                />

                <span class="blue-link"> Ratings 49 </span>

                <q-separator vertical class="q-mx-sm" />

                <span class="blue-link"> 24 Answered Questions </span>
              </div>

              <div class="brand-line">
                Brand:
                <span class="blue-link">No Brand</span>
                <span class="q-mx-sm">|</span>
                <span class="blue-link">
                  More Shoes & Clothing from No Brand
                </span>
              </div>

              <q-separator class="q-my-lg" />

              <div class="price-main">৳ 341</div>

              <div class="price-old">৳ 370</div>

              <div class="option-block">
                <span class="option-title"> Color Family </span>

                <div class="color-option">
                  <q-btn outline color="orange" padding="4px">
                    <q-img
                      :src="images[0]"
                      width="45px"
                      height="45px"
                      fit="cover"
                    />
                  </q-btn>

                  <span class="q-ml-sm"> Blue </span>
                </div>
              </div>

              <div class="option-block">
                <span class="option-title"> Size </span>

                <div class="size-list">
                  <q-btn
                    v-for="size in sizes"
                    :key="size"
                    outline
                    :color="selectedSize === size ? 'orange' : 'grey-7'"
                    :label="size"
                    @click="selectedSize = size"
                  />
                </div>
              </div>

              <div class="quantity-row">
                <span class="option-title q-mr-md"> Quantity </span>

                <q-btn
                  flat
                  color="grey"
                  icon="remove"
                  @click="decreaseQuantity"
                />

                <span class="quantity-number">
                  {{ quantity }}
                </span>

                <q-btn flat color="grey" icon="add" @click="quantity++" />
              </div>

              <div class="action-buttons">
                <q-btn
                  class="buy-button"
                  color="light-blue"
                  label="Buy Now"
                  size="lg"
                  no-caps
                  @click="buyNow"
                />

                <q-btn
                  class="cart-button"
                  color="orange"
                  label="Add to Cart"
                  size="lg"
                  no-caps
                  @click="addToCart"
                />
              </div>
            </q-card-section>
          </q-card>
        </div>

        <div class="delivery-column">
          <q-card flat class="delivery-card">
            <q-card-section>
              <div class="side-title">Delivery Options</div>

              <div class="address-row">
                <q-icon name="location_on" size="25px" />

                <div class="address-text">
                  Dhaka, Dhaka North, Banani
                  <br />
                  Road No. 12 - 19
                </div>

                <q-space />

                <span class="change-link"> CHANGE </span>
              </div>

              <q-separator class="q-my-md" />

              <div class="shipping-row">
                <q-icon name="local_shipping" size="25px" />

                <div>
                  Standard Delivery
                  <div class="sub-text">Guaranteed by 23-26 Sep</div>
                </div>

                <q-space />

                <b>৳ 85</b>
              </div>

              <div class="cash-row">
                <q-icon name="payments" size="25px" />

                Cash on Delivery Available
              </div>

              <q-separator class="q-my-lg" />

              <div class="side-title">Return & Warranty</div>

              <div class="return-row">
                <q-icon name="autorenew" size="25px" />

                14 days easy return
              </div>

              <div class="return-row">
                <q-icon name="verified_user" size="25px" />

                Warranty not available
              </div>

              <q-separator class="q-my-lg" />

              <div class="app-area">
                <div class="qr-box">
                  <q-icon name="qr_code_2" size="80px" />

                  <div class="text-caption">Scan with mobile</div>
                </div>

                <q-separator vertical />

                <div class="app-info">
                  <q-icon name="shopping_cart" color="orange" size="40px" />

                  <div class="text-body2 q-mt-sm">
                    Daraz app to enjoy<br />
                    exclusive design
                  </div>
                </div>
              </div>

              <q-separator class="q-my-lg" />

              <div class="seller-head">
                <div>
                  <div class="text-grey">Sold by</div>

                  <div class="seller-name">Samaro</div>
                </div>

                <q-btn flat color="blue" icon="chat" label="Chat Now" no-caps />
              </div>

              <q-separator class="q-my-md" />

              <div class="seller-stats">
                <div>
                  <div class="text-grey">Positive Seller Ratings</div>
                  <b>80%</b>
                </div>

                <div>
                  <div class="text-grey">Ship on Time</div>
                  <b>100%</b>
                </div>

                <div>
                  <div class="text-grey">Chat Response Rate</div>
                  <b>Not enough</b>
                </div>
              </div>
            </q-card-section>
          </q-card>
        </div>
      </div>

      <q-card flat bordered class="details-card">
        <div class="details-heading">Product details of</div>

        <div class="details-content">
          <ul>
            <li>Jersey for Man</li>
            <li>Club Jersey</li>
            <li>Product Type: Jersey</li>
            <li>Print: 100% Quality</li>
            <li>Sublamination Print</li>
            <li>Color: 100% Guarantee</li>
            <li>Product: Same as Design</li>
            <li>Main Material: Chinigura Fabric</li>
            <li>Gender: Men/Woman</li>
            <li>Stylish and Comfortable</li>
          </ul>

          <div class="detail-group">
            <ul>
              <li>Size: M, L, XL, XXL</li>
              <li>Size: M-Length 26, Chest 36</li>
              <li>Size: L-Length 27, Chest 38</li>
              <li>Size: XL-Length 28, Chest 40</li>
              <li>Size: XXL-Length 29, Chest 42</li>
              <li>Size: 3XL-Length 30, Chest 44</li>
            </ul>
          </div>

          <div class="description-text">
            <p>
              We provide fashionable trendy and good quality product. We always
              ensure the best quality product. Our products are very comfortable
              to use. Please choose the right size while placing an order.
            </p>

            <div class="hashtags">
              #jersey<br />
              #jersey football<br />
              #football jersey<br />
              #জার্সি
            </div>
          </div>

          <q-separator class="q-my-lg" />

          <ul>
            <li>Jersey for Man</li>
            <li>Club Jersey</li>
            <li>Product Type: Jersey</li>
            <li>Print: 100% Quality</li>
            <li>Sublamination Print</li>
            <li>Color: 100% Guarantee</li>
            <li>Product: Same as Design</li>
            <li>Main Material: Chinigura Fabric</li>
            <li>Gender: Men/Woman</li>
          </ul>

          <div class="custom-note">
            নাম এবং নাম্বার দিয়ে টি-শার্ট (Customized) করতে চাইলে আমাদের fb পেজ
            থেকে নিতে হবে। fb পেজ নাম bdbazar06
          </div>

          <q-separator class="q-my-lg" />

          <div class="spec-heading">Specifications of</div>

          <div class="spec-grid">
            <div>
              <div class="spec-item">
                <div class="spec-label">Brand</div>
                <div>No Brand</div>
              </div>

              <div class="spec-item">
                <div class="spec-label">Top type</div>
                <div>T-Shirts</div>
              </div>

              <div class="spec-item">
                <div class="spec-label">Clothing Material</div>
                <div>Jersey</div>
              </div>

              <div class="spec-item">
                <div class="spec-label">Sports Features</div>
                <div>Football Jersey</div>
              </div>

              <div class="spec-item">
                <div class="spec-label">Sport Type</div>
                <div>Football Jersey</div>
              </div>
            </div>

            <div>
              <div class="spec-item">
                <div class="spec-label">SKU</div>
                <div>567029973_BD-12686358082</div>
              </div>

              <div class="spec-item">
                <div class="spec-label">Sport Features</div>
                <div>Football Jersey</div>
              </div>

              <div class="spec-item">
                <div class="spec-label">Main Material</div>
                <div>Poly-Cotton</div>
              </div>

              <div class="spec-item">
                <div class="spec-label">Model</div>
                <div>New & Latest</div>
              </div>
            </div>
          </div>

          <q-separator class="q-my-lg" />

          <div class="box-row">
            <div class="box-label">What's in the box</div>

            <div>Thai Premium Football Jersey - Jersey</div>
          </div>

          <q-separator class="q-my-md" />

          <div class="button-center">
            <q-btn
              outline
              color="primary"
              label="VIEW LESS"
              padding="9px 30px"
              no-caps
            />
          </div>
        </div>
      </q-card>

      <q-card flat bordered class="review-card">
        <q-card-section>
          <div class="review-heading">
            Ratings & Reviews of Brazil World Cup Jersey 2026
          </div>
        </q-card-section>

        <q-separator />

        <q-card-section>
          <div class="rating-summary">
            <div class="rating-score">
              <div class="score-number">4.4<span>/5</span></div>

              <q-rating
                :model-value="4.4"
                max="5"
                size="32px"
                color="orange"
                readonly
                icon="star_border"
                icon-selected="star"
                icon-half="star_half"
              />

              <div class="score-count">49 Ratings</div>
            </div>

            <div class="rating-breakdown">
              <div
                v-for="item in ratingDistribution"
                :key="item.stars"
                class="rating-item"
              >
                <div class="rating-stars">
                  <q-rating
                    :model-value="item.stars"
                    max="5"
                    size="18px"
                    color="orange"
                    readonly
                  />
                </div>

                <q-linear-progress
                  :value="item.count / 49"
                  color="orange"
                  track-color="grey-3"
                  rounded
                  size="10px"
                  class="rating-progress"
                />

                <div class="rating-count">
                  {{ item.count }}
                </div>
              </div>
            </div>
          </div>
        </q-card-section>

        <q-separator />

        <div class="review-toolbar">
          <div class="text-subtitle1">Product Reviews</div>

          <q-space />

          <q-btn
            flat
            no-caps
            icon="swap_vert"
            label="Sort: Relevance"
            color="grey-8"
          />

          <q-separator vertical />

          <q-btn
            flat
            no-caps
            icon="filter_alt"
            label="Filter: All star"
            color="grey-8"
          />
        </div>

        <q-separator />

        <q-list separator>
          <q-item
            v-for="(review, index) in reviews"
            :key="index"
            class="review-item"
          >
            <q-item-section>
              <q-rating
                :model-value="review.rating"
                max="5"
                size="22px"
                color="orange"
                readonly
              />

              <div class="review-user">
                <span>
                  {{ review.user }}
                </span>

                <span class="verified">
                  <q-icon name="check_circle" size="15px" />
                  Verified Purchase
                </span>
              </div>

              <div class="review-text">
                {{ review.text }}
              </div>

              <div v-if="review.images.length" class="review-image-area">
                <q-carousel
                  v-model="review.slide"
                  animated
                  swipeable
                  navigation
                  arrows
                  height="180px"
                  control-color="orange"
                  class="review-carousel"
                >
                  <q-carousel-slide
                    v-for="(photo, photoIndex) in review.images"
                    :key="photoIndex"
                    :name="photoIndex"
                    class="image-slide"
                  >
                    <q-img
                      :src="photo"
                      fit="contain"
                      class="full-width full-height"
                    />
                  </q-carousel-slide>
                </q-carousel>
              </div>

              <div class="helpful-row">
                <q-btn
                  flat
                  dense
                  color="grey-6"
                  icon="thumb_up"
                  :label="String(review.helpful)"
                  no-caps
                />
              </div>
            </q-item-section>

            <q-item-section side>
              <q-btn flat round dense icon="more_vert" color="grey-7" />
            </q-item-section>
          </q-item>
        </q-list>

        <q-separator />

        <div class="pagination-area">
          <q-pagination
            v-model="reviewPage"
            :max="10"
            direction-links
            boundary-links
            color="grey-5"
            active-color="light-blue"
            active-text-color="white"
          />
        </div>
      </q-card>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

import productOne from "src/assets/ab121 (35).png";
import productTwo from "src/assets/ab121 (35).png";
import productThree from "src/assets/ab121 (36).png";
import productFour from "src/assets/ab121 (35).png";
import productFive from "src/assets/ab121 (36).png";

const search = ref("");
const slide = ref(0);
const quantity = ref(1);
const selectedSize = ref("XXL");
const reviewPage = ref(1);

const images = [productOne, productTwo, productThree, productFour, productFive];

const sizes = ["M", "L", "XL", "XXL"];

const ratingDistribution = [
  { stars: 5, count: 37 },
  { stars: 4, count: 4 },
  { stars: 3, count: 2 },
  { stars: 2, count: 4 },
  { stars: 1, count: 2 },
];

const reviews = ref([
  {
    user: "SarahM_92",
    rating: 5,
    text: "Good product 💙 but the size was a little confusing. I ordered one size bigger after checking another review and it fits perfectly.",
    images: [productOne],
    slide: 0,
    helpful: 0,
  },
  {
    user: "রাকিব হাসান",
    rating: 5,
    text: "জার্সি টা অনেক ভালো ছিল। আমি L সাইজ অর্ডার করেছিলাম এবং সাইজ একদম ঠিক হয়েছে। কাপড়ও ভালো এবং দেখতে ছবির মতোই।",
    images: [productTwo],
    slide: 0,
    helpful: 0,
  },
  {
    user: "Mike_Johnson",
    rating: 4,
    text: "Good jersey for the price. The quality is decent and it looks nice. The logo could be a little better, but overall I am happy with the purchase.",
    images: [productThree, productFour],
    slide: 0,
    helpful: 0,
  },
  {
    user: "Nusrat Jahan",
    rating: 5,
    text: "Product ta picture er motoi peyechi. Fabric comfortable and size tao perfect hoyeche. Delivery o time moto peyechi.",
    images: [productFive],
    slide: 0,
    helpful: 0,
  },
  {
    user: "David_Wilson",
    rating: 4,
    text: "The jersey looks good and feels comfortable. The material is decent for the price and the overall fitting is good.",
    images: [productFour, productFive],
    slide: 0,
    helpful: 0,
  },
  {
    user: "সাইফুল ইসলাম",
    rating: 5,
    text: "দাম অনুযায়ী প্রোডাক্ট অনেক ভালো। কালার এবং ডিজাইন ছবির মতোই পেয়েছি। সাইজও ঠিক ছিল।",
    images: [productTwo],
    slide: 0,
    helpful: 0,
  },
]);

function decreaseQuantity() {
  if (quantity.value > 1) {
    quantity.value--;
  }
}

function addToCart() {
  console.log(selectedSize.value, quantity.value);
}

function buyNow() {
  console.log(selectedSize.value, quantity.value);
}
</script>

<style lang="sass" scoped>
.shop-page
  min-height: 100vh
  background: #f5f5f5
  color: #333

.top-area
  background: #f57224
  color: white

.top-links
  display: flex
  justify-content: flex-end
  align-items: center
  gap: 24px
  padding: 6px 40px
  font-size: 12px

.main-header
  display: flex
  align-items: center
  padding: 8px 40px 18px
  gap: 18px

.logo-icon
  display: flex
  align-items: center

.brand-title
  width: 120px
  font-size: 30px
  font-weight: 700

.search-area
  flex: 1

.search-tags
  margin-top: 4px
  font-size: 12px

.cart-area
  width: 70px
  text-align: center

.category-area
  background: white
  padding: 0 40px

.content-area
  padding: 28px 40px

.breadcrumb
  color: #0088cc
  margin-bottom: 20px
  font-size: 14px

.product-layout
  display: grid
  grid-template-columns: 4fr 5fr 3fr
  gap: 16px
  align-items: start

.gallery-card
  background: white

.image-slide
  padding: 0
  background: white

.thumbnail-list
  display: flex
  gap: 8px
  margin-top: 10px
  overflow-x: auto

.thumbnail-card
  cursor: pointer
  background: white
  border: 1px solid #ddd

.thumbnail-active
  border: 2px solid #f57224

.product-card
  background: white

.product-title
  font-size: 20px
  line-height: 1.45
  font-weight: 500

.rating-line
  display: flex
  align-items: center
  margin-top: 16px

.blue-link
  color: #1683c7
  margin-left: 8px
  cursor: pointer

.brand-line
  margin-top: 24px
  font-size: 14px

.price-main
  color: #f57224
  font-size: 30px
  font-weight: 600

.price-old
  color: #999
  text-decoration: line-through
  margin-top: 3px

.option-block
  margin-top: 24px

.option-title
  display: block
  color: #777
  font-size: 14px

.color-option
  display: flex
  align-items: center
  margin-top: 8px

.size-list
  display: flex
  gap: 8px
  margin-top: 10px
  flex-wrap: wrap

.quantity-row
  display: flex
  align-items: center
  margin-top: 24px

.quantity-number
  min-width: 35px
  text-align: center

.action-buttons
  display: flex
  gap: 10px
  margin-top: 24px

.buy-button
  flex: 1

.cart-button
  flex: 1

.delivery-card
  background: white

.side-title
  font-size: 16px
  font-weight: 700

.address-row
  display: flex
  align-items: flex-start
  gap: 8px
  margin-top: 18px

.address-text
  line-height: 1.5
  font-size: 14px

.change-link
  color: #1683c7
  font-size: 12px

.shipping-row
  display: flex
  align-items: center
  gap: 10px

.sub-text
  color: #999
  font-size: 13px
  margin-top: 3px

.cash-row
  display: flex
  align-items: center
  gap: 10px
  margin-top: 22px

.return-row
  display: flex
  align-items: center
  gap: 10px
  margin-top: 20px

.app-area
  display: flex
  align-items: center
  justify-content: center
  gap: 15px

.qr-box
  text-align: center

.app-info
  text-align: center

.seller-head
  display: flex
  align-items: center
  justify-content: space-between

.seller-name
  font-size: 20px
  margin-top: 4px

.seller-stats
  display: grid
  grid-template-columns: repeat(3, 1fr)
  gap: 10px
  font-size: 12px

.details-card
  background: white
  margin-top: 24px

.details-heading
  padding: 18px 22px
  background: #f7f7f7
  font-size: 18px
  font-weight: 700

.details-content
  padding: 22px
  line-height: 1.7

.details-content ul
  margin: 0
  padding-left: 24px

.detail-group
  margin-top: 20px

.description-text
  margin-top: 20px

.description-text p
  margin: 0

.hashtags
  margin-top: 8px
  margin-left: 20px

.custom-note
  margin-top: 18px

.spec-heading
  font-size: 18px
  font-weight: 700

.spec-grid
  display: grid
  grid-template-columns: 1fr 1fr
  gap: 40px
  margin-top: 18px

.spec-item
  margin-bottom: 18px

.spec-label
  color: #777
  margin-bottom: 3px

.box-row
  display: grid
  grid-template-columns: 170px 1fr
  align-items: center

.box-label
  color: #777

.button-center
  display: flex
  justify-content: center
  margin-top: 18px

.review-card
  background: white
  margin-top: 28px

.review-heading
  font-size: 18px
  font-weight: 500

.rating-summary
  display: grid
  grid-template-columns: 280px 1fr
  gap: 40px

.score-number
  font-size: 48px
  line-height: 1
  margin-bottom: 8px

.score-number span
  font-size: 22px
  color: #999

.score-count
  color: #999
  margin-top: 5px

.rating-breakdown
  max-width: 500px

.rating-item
  display: flex
  align-items: center
  margin-bottom: 8px

.rating-stars
  width: 100px

.rating-progress
  flex: 1
  margin: 0 15px

.rating-count
  width: 30px
  color: #777

.review-toolbar
  display: flex
  align-items: center
  padding: 12px 20px

.review-item
  padding-top: 24px
  padding-bottom: 24px

.review-user
  display: flex
  align-items: center
  gap: 10px
  margin-top: 5px
  color: #999
  font-size: 13px

.verified
  display: flex
  align-items: center
  gap: 4px
  color: #21a366

.review-text
  margin-top: 14px
  line-height: 1.6

.review-image-area
  margin-top: 14px

.review-carousel
  width: 250px
  background: #f5f5f5
  border-radius: 4px

.helpful-row
  margin-top: 10px

.pagination-area
  display: flex
  justify-content: flex-end
  padding: 20px

@media (max-width: 1100px)
  .product-layout
    grid-template-columns: 1fr

  .delivery-column
    width: 100%

  .rating-summary
    grid-template-columns: 1fr

@media (max-width: 700px)
  .top-links
    display: none

  .main-header
    padding: 12px 15px
    gap: 8px

  .brand-title
    width: auto
    font-size: 22px

  .logo-icon
    display: none

  .content-area
    padding: 15px

  .category-area
    padding: 0 15px

  .product-title
    font-size: 18px

  .spec-grid
    grid-template-columns: 1fr

  .box-row
    grid-template-columns: 1fr
    gap: 8px

  .action-buttons
    flex-direction: column

  .seller-stats
    grid-template-columns: 1fr

  .review-toolbar
    flex-wrap: wrap
    gap: 5px
</style>
