<template>
  <div>
    <div id="panolens"></div>

    <div id="desc-container" style="display: none">
      <h1>Voyage vers l'inconnu</h1>
      <div class="text">
        Voyage vers l'inconnu, vers des horizons lointains, avec des vents qui
        soufflent, et des vagues qui se brisent. A chaque nouvelle étape, une
        nouvelle histoire, une nouvelle rencontre, une nouvelle mémoire. De
        chaque destination, nous ramenons un peu de nous, et laissons un peu de
        nous, dans chaque coin de cette terre. Voyage vers l'inconnu, c'est
        s'émerveiller, c'est se découvrir, et se réinventer.
      </div>
    </div>

    <div id="desc-divine" style="display: none">
      <h1>HAUTE JOAILLERIE</h1>
      <h2>Collection Divine</h2>
      <h3>Création « Divine »..</h3>
      <div class="text">
        Née de l'imagination de Katia Lobata, femme moderne.
        <br />
        fondatrice des Demoiselles à Versailles.
        <br />
        Elle met en valeur le savoir-faire français à travers la Haute
        Joaillerie et rend hommage à sa grand-mère, danseuse talentueuse et
        divine ...
        <br />
        L'âme de ce collier est inspirée des jardins à la française.
        <br />
        Or jaune, tsavorites, saphirs, rubis et diamants.
        <br />
        Gemme centrale: grenat spessartite (Nigéria) de 10.40 carats
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import * as THREE from 'three'

export default {
  data: () => {
    import('@enra-gmbh/panolens').then(
      ({ ImagePanorama, Viewer, Infospot, DataImage }) => {
        const container = document.querySelector('#panolens') as HTMLElement

        const panorama = new ImagePanorama('/panorama.jpg')

        const infospot1 = new Infospot(40)
        const scale = 0.1
        infospot1.position.set(-2082.3, -1848.42, -4143.26)
        infospot1.position.multiplyScalar(scale)
        const descDivine = document.getElementById('desc-divine') as HTMLElement
        infospot1.addHoverElement(descDivine, -container.offsetTop - 180)
        panorama.add(infospot1)

        const infospot2 = new Infospot(300, DataImage.Info)
        const descContainer = document.getElementById(
          'desc-container'
        ) as HTMLElement
        infospot2.position.set(-4300.83, -235.09, -2528.17)
        infospot2.addHoverElement(descContainer, -container.offsetTop + 200)
        panorama.add(infospot2)

        const view = new Viewer({
          container,
          autoRotate: true,
          autoRotateSpeed: -1,
          autoRotateActivationDuration: 5000,
          output: 'console',
        })

        for (const element of [
          { x: 2603.4, y: -1712.69, z: -3897.96, s: 200 },
          { x: 808.74, y: -3020.1, z: -3897.1, s: 300 },
          { x: -3856.71, y: -3076.43, z: -780.31, s: 300 },
          { x: -4520.63, y: -1813.5, z: 1094.55, s: 200 },
          { x: -4490.07, y: -1118.0, z: 1878.29, s: 100 },
        ]) {
          const infospot = new Infospot(element.s, DataImage.Info)
          infospot.position.set(element.x, element.y, element.z)
          infospot.addHoverText('Transat', -container.offsetTop + 50)
          panorama.add(infospot)
        }

        view.add(panorama)

        const loader = new THREE.TextureLoader()
        loader.load('/sprite4.png', function (texture) {
          const scale = 3
          const geometry = new THREE.PlaneGeometry(258 * scale, 693 * scale)
          const material = new THREE.MeshBasicMaterial({
            map: texture,
            opacity: 1,
            side: THREE.DoubleSide,
            transparent: true,
          })

          const sprite = new THREE.Mesh(geometry, material)

          // Offset the hotspot so it is below the view origin [Updated]
          sprite.position.set(+150, -100, -300)
          sprite.position.multiplyScalar(7.0)

          const rotation = new THREE.Matrix4()
          rotation.makeRotationAxis(new THREE.Vector3(0, 1, 0), 2.5 + 3.14)
          view.add(sprite)
          sprite.rotation.setFromRotationMatrix(rotation)
        })
      }
    )
  },
}
</script>

<style>
#panolens {
  width: 100vw;
  height: 75vh;
  margin: 0;
  padding: 0;
}

#desc-container,
#desc-divine {
  font-size: 15px;
  max-width: 500px;
  max-height: 400px;
  min-width: 200px;
  background: rgb(255 255 255 / 70%);
  backdrop-filter: blur(5px);
  color: #000;
  border-radius: 20px;
  overflow: auto;
  margin: 20px;
  padding: 20px;
  box-shadow: 0 10px 10px 5px rgba(0 0 0 / 30%);
  transition: backdrop-filter 1s;
}

#desc-container > iframe,
#desc-divine > iframe {
  border: none;
  width: 100%;
}

.text {
  text-align: center;
}

h1,
h2,
h3 {
  text-align: center;
  margin: 0;
}
</style>
