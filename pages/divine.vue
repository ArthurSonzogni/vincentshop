<template>
  <div id="main">
    <GlobalStyle />

    <div class="head">
      <div class="main-wrapper">
        <img id="header-img" src="/DSC_8743-12.jpg" />
      </div>
    </div>

    <MyParagraph class="dark">
      <MyDivineDescription />
    </MyParagraph>

    <MyGallery />
    <MyFooter />
  </div>
</template>

<style scoped>
div {
  margin: 0;
  padding: 0;
}

.main-wrapper {
  max-width: 500px;
  margin-left: auto;
  margin-right: auto;
}

#header-img {
  width: 100%;
  box-shadow: inset 0 0 50px 0 #202020;
  margin: 0;
  padding: 0;
}

.head {
  background-color: #202020;
  box-shadow: 0 0 40px 0 #202020;
}

#container {
  scroll-snap-type: y proximity;
}
</style>
