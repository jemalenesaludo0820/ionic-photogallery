<template>
<ion-page>
  <ion-header>
    <ion-toolbar>
      <ion-title>My Photo Gallery</ion-title>
    </ion-toolbar>
  </ion-header>

  <ion-content class="ion-padding">
    <CameraComponents @photoCaptured="addPhoto" />
    <PhotoGalleryComponents :photos="photos" />
  </ion-content>
  </ion-page>
  </template>

  <script setup lang="ts">
  import {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar
  } from '@ionic/vue';
  import { ref } from 'vue';
  import CameraComponents from '@/components/CameraComponents.vue';
  import PhotoGalleryComponents from '@/components/PhotoGalleryComponents.vue';
const photos = ref<string[]>([]);

  const addPhoto = (photo: string) => {
    photos.value.unshift(photo);
  };
  </script>