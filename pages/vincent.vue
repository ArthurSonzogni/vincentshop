<template>
  <div id="main">
    <MyHeader />

    <MyParagraph class="dark center">
      Depuis plus de 100 ans, la passion de Vincent Arnould anime ses créations
      de haute joaillerie. La Maison transmet sa conception particulière du
      métier, qui se caractérise par des sources d'inspiration envoûtantes et un
      savoir-faire virtuose. Chaque pierre est minutieusement choisie pour sa
      qualité remarquable et l'émotion qu'elle véhicule.
    </MyParagraph>

    <MyPanolens />

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

    <MyParagraph class="dark">
      Depuis plus de 100 ans, la passion de Vincent Arnould anime ses créations
      de haute joaillerie. La Maison transmet sa conception particulière du
      métier, qui se caractérise par des sources d'inspiration envoûtantes et un
      savoir-faire virtuose. Chaque pierre est minutieusement choisie pour sa
      qualité remarquable et l'émotion qu'elle véhicule.
    </MyParagraph>

    <MyFooter />
  </div>
</template>

<script>
if (global.window !== undefined && window.document) {
  const originalCreateElement = document.createElement
  document.createElement = function () {
    const element = originalCreateElement.apply(this, arguments)
    if (element instanceof HTMLIFrameElement) {
      element.credentialless = true
    }
    return element
  }
}
</script>

<style>
html,
body,
p {
  margin: 0;
  padding: 0;
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
</style>
