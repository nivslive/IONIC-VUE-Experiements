<template>
    <ion-app class="ion-app">

      <ion-content fullscreen class="ion-padding" scroll-y="false">
        <TestPage  position="fixed" />
        <ion-slides>
          <ion-slide>
            <Example />
            <div class="slide">
              <img src="/assets/icon/icon.png" />
              <h1> oi! </h1>
              <h2>Welcome</h2>
              <p>
                The <b>ionic conference app</b> is a practical preview of the ionic framework in action, and a
                demonstration of proper code use.
              </p>
              
            </div>
          </ion-slide>

          <ion-slide>
            <img src="/assets/icon/icon.png" />
            <h2>What is Ionic?</h2>

            <ion-grid>
              <InputTest />
              <ion-row>
                {{ login }}
                <ion-col class="ion-margin-vertical"> <ion-input placeholder="Custom input" v-model="login" 
                  :value="login"
                  @ionInput="login = $event.target.value;"
                  class="custom"></ion-input></ion-col>
              </ion-row>
            </ion-grid>


            <p>
              <b>Ionic Framework</b> is an open source SDK that enables developers to build high quality mobile apps
              with web technologies like HTML, CSS, and JavaScript.
            </p>
          </ion-slide>

          <ion-slide>
            <img src="/assets/icon/icon.png" />
            <h2>What is Appflow?</h2>
            <p>
              <b>Appflow</b> is a powerful set of services and features built on top of Ionic Framework that brings a
              totally new level of app development agility to mobile dev teams.
            </p>
          </ion-slide>

          <ion-slide>
            <img src="/assets/icon/icon.png" />
            <h2>Ready to Play?</h2>
            <ion-button fill="clear">Continue <ion-icon slot="end" name="arrow-forward"></ion-icon></ion-button>
          </ion-slide>
        </ion-slides>
      </ion-content>
    </ion-app>
    <Test />
    <Pug />
</template>
<style scoped src="./App.css" />
<style scoped>
      ion-app {
        --ion-background-color:#000000;
        --ion-text-color: #ffffff;
      }
      ion-slides {
        height: 100%;
      }

      .swiper-slide {
        display: block;
      }

      .swiper-slide h2 {
        margin-top: 2.8rem;
      }

      .swiper-slide img {
        max-height: 50%;
        max-width: 80%;
        margin: 60px 0 40px;
        pointer-events: none;
      }

      b {
        font-weight: 500;
      }

      p {
        padding: 0 40px;
        font-size: 14px;
        line-height: 1.5;
        color: var(--ion-color-step-600, #60646b);
      }

      p b {
        color: var(--ion-text-color, #000000);
      }
</style>
<script>
import { IonSlides, IonSlide, IonApp, IonContent } from '@ionic/vue';
import  InputTest  from './views/form/InputTest.vue';
import { defineComponent } from 'vue';
import TestPage from './views/TestPage.vue';
import Test from './Test.vue';
import Example from './views/navs/Example.vue';
import Pug from './Pug.vue';

export default defineComponent({
  components: { IonSlides, IonSlide, IonApp, IonContent, TestPage, Example, Test, InputTest, Pug },
  data() {
    return {
      login: ''
    }
  },
  setup() {
    // Optional parameters to pass to the swiper instance. See https://swiperjs.com/swiper-api for valid options.
    const slideOpts = {
      initialSlide: 1,
      speed: 400
    };
    return { slideOpts }
  }
});
</script>