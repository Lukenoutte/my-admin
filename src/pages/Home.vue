<template>
  <q-page>
  <div class="q-pa-md">
    <q-carousel
      v-model="slide"
      swipeable
      animated
      control-color="primary"
      navigation
      padding
      arrows
      height="300px"
      class="text-primary rounded-borders shadow-1"
    >
      <q-carousel-slide name="style" class="column no-wrap flex-center">
        <q-icon name="style" size="56px" />
        <div class="q-mt-md text-center text-black">
          {{ lorem }}
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="tv" class="column no-wrap flex-center">
        <q-icon name="live_tv" size="56px" />
        <div class="q-mt-md text-center text-black">
          {{ lorem }}
        </div>
      </q-carousel-slide>
    </q-carousel>
  </div>
  </q-page>
</template>

<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'Home',
  setup () {
    const slide = ref('style')
    return {
      slide,
      lorem: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Itaque voluptatem totam, architecto cupiditate officia rerum, error dignissimos praesentium libero ab nemo.'
    }
  }
})
</script>