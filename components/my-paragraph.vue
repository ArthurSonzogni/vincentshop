<template>
  <div class="paragraph-container">
    <p class="paragraph">
      <slot />
    </p>
  </div>
</template>

<style scoped>
.paragraph {
  margin: 0;
  padding: 30px;
  max-width: 700px;
  margin-left: auto;
  margin-right: auto;
}

.paragraph-container.light {
  background-color: rgb(255 255 255 / 5%);
}

.paragraph-container.dark {
  background-color: rgb(0 0 100 / 5%);
}

.paragraph-container.center {
  text-align: center;
}
</style>
