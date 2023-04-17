<template>
     <section class="card" :class="{ 'card-reverse': data.reverse }">
          <div class="card---photo">
               <img class="card---icon" src="../assets/icons/heart.png" alt="heart" />
               <img class="card---img" src="../assets/imgs/photoOne.jpg" alt="photoOne" />
          </div>
          <div class="card---content">
               <h1 class="card---content--title">{{ data.title }}</h1>
               <p class="card---content--subtitle">{{ data.subtitle }}</p>
               <a class="card---content--btn" :href="data.link">
                    <div class="card---content--btn-text">SHOP NOW</div>
                    <div class="card---content--btn-arrow"></div>
               </a>
          </div>
     </section>
</template>

<script setup lang="ts">
import { defineProps } from "vue";
const props = defineProps({ data: {} });
</script>

<style scoped lang="scss">
@import "../assets/styles/style.scss";
.card {
     display: flex;
     flex-flow: column;
     margin: 10px;
     width: 30%;

     .card---photo {
          position: relative;
          width: 100%;

          .card---icon {
               display: block;
               position: absolute;
               width: 20px;
               right: 30px;
               top: 30px;
               padding: 10px;
               border-radius: 20px;
               background-color: #fff;
          }

          .card---img {
               width: 100%;
          }
     }

     .card---content {
          @extend %flex--vertical;
          flex-flow: column;
          text-align: center;

          .card---content--title {
               font-weight: 200;
               margin: 40px 0px 0px 0px;
               font-size: 21px;
          }

          .card---content--subtitle {
               font-weight: 100;
               margin: 15px 0px 0px 0px;
               font-size: 16px;
          }

          .card---content--btn {
               @extend %flex--vertical;
               width: 200px;
               position: relative;
               margin: 35px;
               height: 20px;
               text-decoration: none;
               color: $primary-color;

               .card---content--btn-text {
                    width: 100%;
                    text-align: center;
                    font-size: 14px;
               }

               .card---content--btn-arrow {
                    position: absolute;
                    @extend %flex--vertical-horizontal;
                    left: 150px;
                    background-color: $primary-color;
                    height: 3px;
                    width: 18px;

                    &::after,
                    &::before {
                         content: "";
                         display: block;
                         position: absolute;
                         background-color: $primary-color;
                         height: 3px;
                         width: 10px;
                    }

                    &::after {
                         transform: rotate(45deg);
                         margin: 0px 0px 5px 12px;
                    }

                    &::before {
                         transform: rotate(-45deg);
                         margin: 0px 0px -5px 12px;
                    }
               }

               &:hover {
                    .card---content--btn-arrow {
                         transform: translate(5px, 0px);
                         transition-duration: 0.5s;
                    }
               }
          }
     }
}

.card-reverse {
     display: flex;
     flex-direction: column-reverse;
}
</style>
