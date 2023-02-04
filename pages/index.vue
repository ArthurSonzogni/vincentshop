<template>
  <div id="main">
    <GlobalStyle />
    <MyHeaderDv />

    <MyDvVersaille id="my-panolens-versaille" />

    <MyParagraph class="dark">
      <MyDivineDescription />
    </MyParagraph>
    <MyParagraph class="light">
      <h2>Une collection & un savoir-faire</h2>
      Une collection unique inspirée des jardins à la française et de
      l’Orangerie du Château de Versailles.
    </MyParagraph>

    <MyParagraph class="dark">
      <h2>IRRÉSISTIBLES TENTATIONS</h2>
      Avec ses lignes pures imaginées par Jules Hardouin-Mansart et son jardin
      peuplé d’orangers, de citronniers, de lauriers roses et de grenadiers,
      l’Orangerie du Château de Versailles est à la fois un plaisir pour les
      sens et un chef-d’œuvre de l’architecture.
    </MyParagraph>

    <MyGallery />

    <MyFooter />
  </div>
</template>

<style scoped>
p {
  margin-bottom: 20px;
}

html,
body {
  overflow-x: hidden;
}

body {
  background-color: #f5f5f5;
  text-rendering: optimizelegibility;
  font-family: 'Maison Neue', sans-serif;
  font-size: calc(15px + 0.3906vw);
}

#container {
  scroll-snap-type: y proximity;
}

#my-panolens-versaille {
  scroll-snap-align: start;
}
</style>
