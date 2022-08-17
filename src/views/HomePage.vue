<template>
  <ion-header>
    <ion-toolbar>
      <ion-title>Inline Modal</ion-title>
    </ion-toolbar>
  </ion-header>
  <ion-content class="ion-padding">
    <ion-button expand="block" @click="setOpen(true)">Open</ion-button>

    <ion-modal :is-open="isOpen">
      <ion-header>
        <ion-toolbar>
          <ion-title>Modal</ion-title>
          <ion-buttons slot="end">
            <ion-button @click="setOpen(false)">Close</ion-button>
          </ion-buttons>
        </ion-toolbar>
      </ion-header>
      <ion-content class="ion-padding">
        <ion-accordion-group>
          <ion-accordion value="first">
            <ion-item slot="header" color="light">
              <ion-label>First Accordion</ion-label>
            </ion-item>
            <div class="ion-padding" slot="content">
              First Content
              <div style="height: 600px;background-color: blue;">
                Some Tall Content to Test Scroll
              </div>
            </div>
          </ion-accordion>
          <ion-accordion value="second">
            <ion-item slot="header" color="light">
              <ion-label>Second Accordion</ion-label>
            </ion-item>
            <div class="ion-padding" slot="content">
              Second Content
            </div>
          </ion-accordion>
        </ion-accordion-group>
      </ion-content>
    </ion-modal>
  </ion-content>
</template>

<script lang="ts">
  import { IonButtons, IonButton, IonModal, IonHeader, IonToolbar, IonContent, IonTitle, IonAccordion, IonAccordionGroup } from '@ionic/vue';
  import { defineComponent } from 'vue';

  export default defineComponent({
    components: { IonButtons, IonButton, IonModal, IonHeader, IonContent, IonToolbar, IonTitle, IonAccordion, IonAccordionGroup },
    data() {
      return {
        isOpen: false,
      };
    },
    methods: {
      setOpen(isOpen: boolean) {
        this.isOpen = isOpen;
      },
    },
  });
</script>