<template>
  <div class="gallery">
    <EnlargeableImage src="DSC_8649-1.1-2.jpg" src_large="DSC_8649-1.1-2.jpg" />
    <EnlargeableImage src="DSC_8737-11.jpg" src_large="DSC_8737-11.jpg" />
    <EnlargeableImage src="DSC_8743-12.jpg" src_large="DSC_8743-12.jpg" />
    <EnlargeableImage src="DSC_8808-1.jpg" src_large="DSC_8808-1.jpg" />
    <EnlargeableImage src="DSC_8859.jpg" src_large="DSC_8859.jpg" />
    <EnlargeableImage src="DSC_8867.jpg" src_large="DSC_8867.jpg" />
    <EnlargeableImage src="DSC_8871.jpg" src_large="DSC_8871.jpg" />
    <EnlargeableImage src="DSC_8918.jpg" src_large="DSC_8918.jpg" />
    <EnlargeableImage src="DSC_8977-2.jpg" src_large="DSC_8977-2.jpg" />
    <EnlargeableImage src="DSC_8977-22.jpg" src_large="DSC_8977-22.jpg" />
    <EnlargeableImage src="DSC_9100-4.jpg" src_large="DSC_9100-4.jpg" />
    <EnlargeableImage src="DSC_9108.jpg" src_large="DSC_9108.jpg" />
  </div>
</template>

<script lang="ts">
import EnlargeableImage from '@diracleo/vue-enlargeable-image'

export default {
  components: {
    EnlargeableImage,
  },
}
</script>

<style scoped>
.gallery {
  display: grid;
  grid-gap: 1px;
  border-radius: 100px;
  grid-template-columns: auto auto auto auto;
}

@media (max-width: 600px) {
  .gallery {
    grid-template-columns: auto auto auto;
  }
}

@media (max-width: 400px) {
  .gallery {
    grid-template-columns: auto auto;
  }
}
</style>
