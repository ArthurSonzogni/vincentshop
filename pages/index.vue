<template>
  <div id="main">
    <MyHeaderDv />

    <MyDvVersaille id="my-panolens-versaille" />

    <MyParagraph class="dark">
      <p>
        The High Jewellery designs that come from the imagination of Katia
        Lobato, a modern and ambitious woman, highlight the unique French
        know-how that is recognized internationally.
      </p>

      <p>
        She chooses stones of a rare quality, with a character that generates
        emotion.
      </p>

      <p>
        The signature of Maison DV Divine is recognized by the “DV” and the
        fleur-de-lys that pays homage to royalty, French elegance and the famous
        “French touch”.
      </p>

      <p>
        Our High Jewellery creations are original pieces from Maison DV Divine
        whose quality criteria meet the requirements of the highest French
        jewellery tradition.
      </p>

      <p>
        At every stage of production, the jewels are the subject of attentive
        care, tests and rigorous controls.
      </p>

      <p>
        The jewels are made by hand, precisely adjusted to size, in our Parisian
        workshops by craftsmen and women with exceptional skill.
      </p>

      <p>Each piece is engraved with:</p>

      <ul>
        <li>The name of the metal used</li>
        <li>
          A unique individual number that identifies it and certifies its
          authenticity
        </li>
        <li>The House signature</li>
      </ul>
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

    <MyParagraph class="light">
      La haute joaillerie est un univers fascinant qui regroupe les plus belles
      et les plus précieuses créations de bijoux. Cette forme d'art joaillier
      est réservée aux pièces les plus rares et les plus luxueuses, souvent
      réalisées à la main par des artisans talentueux. Les bijoux de haute
      joaillerie sont généralement fabriqués avec des matériaux précieux tels
      que l'or, le platine et les diamants, mais ils peuvent également être
      ornés de pierres précieuses rares telles que l'émeraude, le saphir et le
      rubis. Les créations de haute joaillerie sont souvent des œuvres d'art
      uniques, avec des designs complexes et élaborés qui mettent en valeur la
      beauté et la qualité des matériaux utilisés. Elles sont destinées à être
      des objets de collection, mais elles peuvent également être portées pour
      des occasions spéciales telles que des mariages ou des soirées de gala. Le
      monde de la haute joaillerie est en constante évolution, avec de nouvelles
      tendances et designs qui émergent chaque année. Les grandes maisons de
      haute joaillerie, telles que Tiffany & Co., Cartier et Van Cleef & Arpels,
      sont reconnues dans le monde entier pour leur savoir-faire exceptionnel et
      leur engagement envers l'excellence. La haute joaillerie est un univers de
      raffinement et de luxe qui fascine et enchante depuis des siècles.
    </MyParagraph>

    <MyFooter />
  </div>
</template>

<style>
html,
body,
p {
  margin: 0;
  padding: 0;
}

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

a:link,
a:visited {
  color: #bdc3c7;
}

body::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}

body::-webkit-scrollbar-track {
  background: transparent;
}

body::-webkit-scrollbar-thumb {
  background-color: rgba(128 128 128 / 50%);
  border-radius: 8px;
}

body::-webkit-scrollbar-thumb:hover {
  background-color: rgba(128 128 128 / 100%);
}

html::-webkit-scrollbar {
  display: none;
}

#container {
  scroll-snap-type: y proximity;
}

#my-panolens-versaille {
  scroll-snap-align: start;
}
</style>
