<template>
  <ion-page>
    <ion-header>
      <ion-toolbar> <ion-title> My Photo Gallery </ion-title> </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
      <camera_component @photo-captured="addPhoto" />
      <photo_gallery_component :photos="photos" />
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { 
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent
} from "@ionic/vue";
import { ref } from "vue";
import camera_component from "@/components/CameraComponents.vue";
import photo_gallery_component from "@/components/PhotoGallery.vue";
const photos = ref<string[]>([]);
const addPhoto = (photo: string) => {
  photos.value.unshift(photo);
};
</script>