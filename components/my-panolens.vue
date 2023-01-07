<template>
  <div>
    <div id="panolens"></div>

    <div id="desc-container" style="display: none">
      <h1>Une chaise magnifique</h1>
      <div class="text">
        Fatigué de souffrir de maux de dos au travail ? Optez pour notre chaise
        ergonomique à 200€ ! Conçue pour offrir un soutien optimal à votre dos
        et à votre corps, cette chaise vous permettra de travailler en toute
        confort et sans douleur. De plus, son design élégant s'intégrera
        parfaitement à votre espace de travail. N'attendez plus pour améliorer
        votre posture et votre bien-être au bureau. Achetez notre chaise
        ergonomique dès maintenant !
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

        const panorama1 = new ImagePanorama('/image2.jpg')
        const panorama2 = new ImagePanorama('/image1.jpg')

        const infospot1 = new Infospot()
        infospot1.position.set(5000.0, -665.23, -3996.49)
        infospot1.addHoverText('Un mur blanc', -container.offsetTop + 50)
        panorama1.add(infospot1)

        const infospot2 = new Infospot(300, DataImage.Info)
        const descContainer = document.getElementById(
          'desc-container'
        ) as HTMLElement
        infospot2.position.set(-5000.0, -1825.25, 197.56)
        infospot2.addHoverElement(descContainer, -container.offsetTop + 200)
        panorama1.add(infospot2)

        const view = new Viewer({
          container,
          autoRotate: true,
          autoRotateSpeed: 1,
          autoRotateActivationDuration: 50000,
          output: 'console',
        })

        view.add(panorama1)
        view.add(panorama2)

        // Pair
        panorama1.link(
          panorama2,
          new THREE.Vector3(-1, -0.8, 0).multiplyScalar(4000)
        )
        panorama2.link(
          panorama1,
          new THREE.Vector3(+1, -0.5, 0).multiplyScalar(4000)
        )

        const loader = new THREE.TextureLoader()
        loader.load('/sprite2.png', function (texture) {
          const geometry = new THREE.PlaneGeometry(258 * 0.1, 693 * 0.1)
          const material = new THREE.MeshBasicMaterial({
            map: texture,
            opacity: 1,
            side: THREE.DoubleSide,
            transparent: true,
          })

          const sprite = new THREE.Mesh(geometry, material)

          sprite.position.set(-60, -10, 30)
          const rotation = new THREE.Matrix4()
          rotation.makeRotationAxis(new THREE.Vector3(0, 1, 0), 2)
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

#desc-container {
  font-size: 15px;
  max-width: 400px;
  max-height: 400px;
  min-width: 200px;
  min-height: 250px;
  background: rgb(255 255 255 / 50%);
  backdrop-filter: blur(20px);
  color: #000;
  border-radius: 20px;
  overflow: auto;
  margin: 20px;
  padding: 20px;
  box-shadow: 0 10px 10px 5px rgba(0 0 0 / 30%);
  transition: backdrop-filter 1s;
}

#desc-container > iframe {
  border: none;
  width: 100%;
}
</style>
