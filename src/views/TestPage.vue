<style scoped>
.grid {
  --ion-grid-width: 100%;
  --ion-grid-height: 100%;
}

ion-col {
  --ion-color: white;
}
</style>
<template>
    <ion-header>
      <ion-toolbar>
        <ion-segment value="all">
          <ion-segment-button value="all">
            All
          </ion-segment-button>
          <ion-button @click="posted()"> Procurar API! </ion-button>
          <ion-segment-button value="favorites">
            Favorites
          </ion-segment-button>
        </ion-segment>
      </ion-toolbar>
    </ion-header>
    <Segment />
    <ion-grid class="grid">
  
      <ion-col><buttonHTML @click="test()"/></ion-col>
      <ion-row v-for="li in list" :key="li.email" class="ion-justify-content-center ion-align-items-center">
        <ion-col><ion-text class="ion-text-center"> {{  li.email }}</ion-text></ion-col>
        <ion-col><ion-text class="ion-text-center"> {{  li.first_name }}</ion-text></ion-col>
        <ion-col><ion-text class="ion-text-center"> {{  li.last_name }}</ion-text></ion-col>
      </ion-row>
      
      <ion-row class="ion-justify-content-center ion-align-items-center">
        <ion-col><ion-text class="ion-text-center"> {{  message.email }}</ion-text></ion-col>
        <ion-col><ion-text class="ion-text-center"> {{  message.first_name }}</ion-text></ion-col>
        <ion-col><ion-text class="ion-text-center"> {{  message.last_name }}</ion-text></ion-col>
      </ion-row>
    </ion-grid>
  </template>
  <script lang="ts">
    import { IonButton, IonHeader, IonSegment, IonSegmentButton, IonToolbar, IonText, IonGrid, IonCol, IonRow } from '@ionic/vue';
    import { defineComponent } from 'vue';
    import ButtonHTML from './ButtonHTML.vue';
    import Segment from './Segment.vue';
    export default defineComponent({
      components: { IonButton, IonHeader, IonSegment, IonSegmentButton, IonToolbar, IonText, IonGrid,  IonCol, IonRow, ButtonHTML, Segment  },
      data() {
        return { 
          list: [{
            email: '',
            first_name: '',
            last_name: '',
          } ],
          message: {
            email: '',
            first_name: '',
            last_name: '',
          } 
      }
      },
      methods: {
        test() {
          console.log(this.list, this.message)
          this.list.push(this.message);
        },
        posted() {  
          fetch('https://reqres.in/api/users').then((message:Response) => message.json())
          .then((message) => 
          { this.message = message.data[0];
            this.list = message.data;
          });
          console.log(this.list)
        }
      }
    });
  </script>