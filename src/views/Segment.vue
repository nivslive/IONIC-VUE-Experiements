<template>
    <ion-segment  @ionChange="changeUnit($event)" value="custom">
      <ion-segment-button value="custom">
        <ion-nav-link router-direction="forward" :component="component.one">
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
  </template>
  
  <script lang="ts">
    import { IonLabel, IonSegment, IonSegmentButton, IonNavLink } from '@ionic/vue';
    import { defineComponent } from 'vue';
import PageOne from './navs/PageOne.vue';
import PageThree from './navs/PageThree.vue';
import PageTwo from './navs/PageTwo.vue';
  
    export default defineComponent({
      components: { IonLabel, IonSegment, IonSegmentButton, IonNavLink },
      data() {
        return {
          component: { 
            'one': PageOne,
            'two': PageTwo,
            'three': PageThree,
           },
        };
      },
      methods: {
        changeUnit(event: any) {
          console.log(event.target.value)
        }
      }
    });
  </script>
  
  <style>
    ion-segment {
    }
    ion-segment-button {
      --indicator-color: #b938ff;
    }
    
    /* Material Design styles */
    ion-segment-button.md {
        --ion-background-color: red;
        --color: #ffffff;
        --color-checked: #dd8fff;
        --indicator-height: 4px;
      }
  
    /* iOS styles */
    ion-segment-button.ios {
      --color: #08a391;
      --color-checked: #fff;
      --border-radius: 20px;
    }
  </style>