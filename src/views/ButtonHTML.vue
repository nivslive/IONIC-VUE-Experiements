<template>
    <ion-button>Custom Button</ion-button>
  </template>
  
  <script lang="ts">
    import { IonButton } from '@ionic/vue';
    import { defineComponent } from 'vue';
  
    export default defineComponent({
      components: { IonButton },
    });
  </script>
  
  <style scoped>
    ion-button {
      --background: #100000;
      --background-hover: #ffffff;
      --background-activated: #88f4be;
      --background-focused: #88f4be;
  
      --color: rgb(255, 255, 255);
  
      --border-radius: 50px;
      --border-color: #000;
      --border-style: solid;
      --border-width: 1px;
  
      --box-shadow: 0 2px 6px 0 rgba(154, 154, 154, 0.25);
  
      --ripple-color: deeppink;
  
      --padding-top: 10px;
      --padding-bottom: 10px;
    }
  </style>