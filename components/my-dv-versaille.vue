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

    <div id="divine" style="display: none">
      <div class="text">
        <h1>HAUTE JOAILLERIE</h1>
        <h2>Collection Divine</h2>
        <h3>Création « Divine »..</h3>
      </div>
      <img src="/DSC_8743-12.jpg" />
    </div>
  </div>
</template>

<script lang="ts">
import * as THREE from 'three'

let once = false
const main = async () => {
  if (once) return
  once = true
  const { ImagePanorama, Viewer, Infospot } = await import(
    '@enra-gmbh/panolens'
  )
  const container = document.querySelector('#panolens') as HTMLElement
  const descDivine = document.getElementById('divine') as HTMLElement

  const panorama = new ImagePanorama('/versaille.jpg')

  const view = new Viewer({
    container,
    autoRotate: true,
    autoRotateSpeed: -1,
    autoRotateActivationDuration: 5000,
    output: 'console',
  })

  view.add(panorama)
  view.tweenControlCenter(new THREE.Vector3(-412.02, -969.71, 4879.54), 0)

  const loader = new THREE.TextureLoader()
  const texture: THREE.Texture = await new Promise((resolve) =>
    loader.load('/sprite3_shadow.png', resolve)
  )

  for (let angle = 0; angle < 2.0 * Math.PI; angle += (Math.PI * 2) / 5) {
    const textureScale = 3
    const geometry = new THREE.PlaneGeometry(
      258 * textureScale,
      693 * textureScale
    )
    const material = new THREE.MeshBasicMaterial({
      map: texture,
      opacity: 1,
      side: THREE.DoubleSide,
      transparent: true,
    })

    // Offset the hotspot so it is below the view origin [Updated]
    const radius = 4000
    const sprite = new THREE.Mesh(geometry, material)
    sprite.position.set(
      radius * Math.cos(angle),
      -969.71,
      radius * Math.sin(angle)
    )
    sprite.position.multiplyScalar(0.7)
    const rotation = new THREE.Matrix4()
    rotation.makeRotationAxis(new THREE.Vector3(0, 1, 0), -angle + 3.1415 / 2)
    view.add(sprite)
    sprite.rotation.setFromRotationMatrix(rotation)

    const infospot1 = new Infospot(20)
    const scale = 0.1
    infospot1.position.set(
      -radius * Math.cos(angle),
      -1500,
      -radius * Math.sin(angle)
    )
    infospot1.position.multiplyScalar(scale)
    infospot1.addHoverElement(descDivine, -container.offsetTop + 220)
    panorama.add(infospot1)
  }
}

export default {
  data: () => {
    if (process.browser) {
      main()
    }
    return {}
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

#divine {
  font-size: 15px;
  max-width: 300px;
  min-width: 200px;
  background: rgb(255 255 255 / 70%);
  backdrop-filter: blur(5px);
  color: #000;
  border-radius: 20px;
  overflow: auto;
  margin: 0;
  padding: 0;
  box-shadow: 0 10px 10px 5px rgba(0 0 0 / 30%);
  transition: backdrop-filter 1s;
}

#desc-container > iframe,
#divine > iframe {
  border: none;
  width: 100%;
}

.text {
  margin: 20px;
  text-align: center;
}

#divine img {
  margin: 0;
  padding: 0;
  width: 100%;
}

h1,
h2,
h3 {
  text-align: center;
  margin: 0;
}
</style>
