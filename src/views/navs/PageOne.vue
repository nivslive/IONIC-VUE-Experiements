<template>
    <ion-header>
      <ion-toolbar>
        <ion-title>Page One</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
      <h1>Page One</h1>
      <ion-nav-link router-direction="forward" :component="component.three">
        <ion-button>Go to Page Two</ion-button>
      </ion-nav-link>


      <ion-nav-link router-direction="forward" :component="component.two">
        <ion-button>Go to Page Two</ion-button>
      </ion-nav-link>






          <ion-segment  @ionChange="changeUnit($event)" value="custom">
          <ion-segment-button value="custom">
            <ion-nav-link router-direction="forward" :component="component.three">
              <ion-label>Custom</ion-label>
            </ion-nav-link>
          </ion-segment-button>
          <ion-segment-button value="segment">
            <ion-nav-link router-direction="forward" :component="component.two">
              <ion-label>Segment</ion-label>
            </ion-nav-link>
          </ion-segment-button>
          <ion-segment-button value="buttons">
            <ion-nav-link router-direction="forward" :component="component.three">
              <ion-label>Custom</ion-label>
            </ion-nav-link>
          </ion-segment-button>
        </ion-segment>
    </ion-content>
  </template>
  
  <script lang="ts">
    import { IonHeader, IonTitle, IonToolbar, IonContent, IonNavLink, IonButton, IonSegment, IonSegmentButton } from '@ionic/vue';
    import PageTwo from './PageTwo.vue';
    import PageThree from './PageThree.vue';
    export default {
      components: { IonHeader, IonTitle, IonToolbar, IonContent, IonNavLink, IonButton, IonSegment, IonSegmentButton },
      data() {
        return {
          component: { 
            'two': PageTwo,
            'three': PageThree,
           },
        };
      },
    };
  </script>


<style scoped>
ion-button {
  --background: #000000;
    --background-hover: #00d5ff;
    --background-activated: #88f4be;
    --background-focused: #88f4be;

    --color: rgb(85, 255, 99);

    --border-radius: 0;
    --border-color: #7bff00;
    --border-style: solid;
    --border-width:  0 0 2px 0 ;

    --box-shadow: 0 2px 6px 0 rgb(0, 0, 0, 0.25);

    --ripple-color: deeppink;

    --padding-top: 10px;
    --padding-bottom: 10px;
}
</style>