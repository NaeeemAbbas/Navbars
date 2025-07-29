<template>
  <div class="flex flex-row items-center justify-center py-5 h-screen md:h-auto bg-[#F8F9FA] relative w-full ">
    <div class="max-w-7xl mx-auto w-full relative overflow-hidden h-full md:h-[40rem] px-4">
      <div
        class="div"
        :style="{
          opacity: isVisible ? 1 : 0,
          transform: `translateY(${isVisible ? 0 : 20}px)`,
          transition: 'opacity 1s ease, transform 1s ease'
        }"
      >
        <h2 class="text-center text-xl md:text-4xl font-bold text-black">
          Get In Touch
        </h2>
        <p class="text-center text-base md:text-lg font-normal text-neutral-700 max-w-md mt-2 mx-auto">
          Have a question or want to learn more? Send us a message!
        </p>
      </div>
      <div class="absolute w-full bottom-0 h-72 md:h-full z-10 ">
        <canvas ref="canvasRef" class="w-full h-full"></canvas>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import * as THREE from 'three'
import ThreeGlobe from 'three-globe'

const canvasRef = ref(null)
const isVisible = ref(false)

// Globe configuration
const globeConfig = {
  pointSize: 4,
  globeColor: "#062056",
  showAtmosphere: true,
  atmosphereColor: "#FFFFFF",
  atmosphereAltitude: 0.1,
  emissive: "#062056",
  emissiveIntensity: 0.1,
  shininess: 0.9,
  polygonColor: "rgba(255,255,255,0.7)",
  ambientLight: "#38bdf8",
  directionalLeftLight: "#ffffff",
  directionalTopLight: "#ffffff",
  pointLight: "#ffffff",
  arcTime: 1000,
  arcLength: 0.9,
  rings: 1,
  maxRings: 3,
  initialPosition: { lat: 22.3193, lng: 114.1694 },
  autoRotate: true,
  autoRotateSpeed: 0.5,
}

const colors = ["#06b6d4", "#3b82f6", "#6366f1"]

const sampleArcs = [
  {
    order: 1,
    startLat: -19.885592,
    startLng: -43.951191,
    endLat: -22.9068,
    endLng: -43.1729,
    arcAlt: 0.1,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 1,
    startLat: 28.6139,
    startLng: 77.209,
    endLat: 3.139,
    endLng: 101.6869,
    arcAlt: 0.2,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 1,
    startLat: -19.885592,
    startLng: -43.951191,
    endLat: -1.303396,
    endLng: 36.852443,
    arcAlt: 0.5,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 2,
    startLat: 1.3521,
    startLng: 103.8198,
    endLat: 35.6762,
    endLng: 139.6503,
    arcAlt: 0.2,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 2,
    startLat: 51.5072,
    startLng: -0.1276,
    endLat: 3.139,
    endLng: 101.6869,
    arcAlt: 0.3,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 2,
    startLat: -15.785493,
    startLng: -47.909029,
    endLat: 36.162809,
    endLng: -115.119411,
    arcAlt: 0.3,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 3,
    startLat: -33.8688,
    startLng: 151.2093,
    endLat: 22.3193,
    endLng: 114.1694,
    arcAlt: 0.3,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 3,
    startLat: 21.3099,
    startLng: -157.8581,
    endLat: 40.7128,
    endLng: -74.006,
    arcAlt: 0.3,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 3,
    startLat: -6.2088,
    startLng: 106.8456,
    endLat: 51.5072,
    endLng: -0.1276,
    arcAlt: 0.3,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 4,
    startLat: 11.986597,
    startLng: 8.571831,
    endLat: -15.595412,
    endLng: -56.05918,
    arcAlt: 0.5,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 4,
    startLat: -34.6037,
    startLng: -58.3816,
    endLat: 22.3193,
    endLng: 114.1694,
    arcAlt: 0.7,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 4,
    startLat: 51.5072,
    startLng: -0.1276,
    endLat: 48.8566,
    endLng: -2.3522,
    arcAlt: 0.1,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 5,
    startLat: 14.5995,
    startLng: 120.9842,
    endLat: 51.5072,
    endLng: -0.1276,
    arcAlt: 0.3,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 5,
    startLat: 1.3521,
    startLng: 103.8198,
    endLat: -33.8688,
    endLng: 151.2093,
    arcAlt: 0.2,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 5,
    startLat: 34.0522,
    startLng: -118.2437,
    endLat: 48.8566,
    endLng: -2.3522,
    arcAlt: 0.2,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 6,
    startLat: -15.432563,
    startLng: 28.315853,
    endLat: 1.094136,
    endLng: -63.34546,
    arcAlt: 0.7,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 6,
    startLat: 37.5665,
    startLng: 126.978,
    endLat: 35.6762,
    endLng: 139.6503,
    arcAlt: 0.1,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 6,
    startLat: 22.3193,
    startLng: 114.1694,
    endLat: 51.5072,
    endLng: -0.1276,
    arcAlt: 0.3,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 7,
    startLat: -19.885592,
    startLng: -43.951191,
    endLat: -15.595412,
    endLng: -56.05918,
    arcAlt: 0.1,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 7,
    startLat: 48.8566,
    startLng: -2.3522,
    endLat: 52.52,
    endLng: 13.405,
    arcAlt: 0.1,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 7,
    startLat: 52.52,
    startLng: 13.405,
    endLat: 34.0522,
    endLng: -118.2437,
    arcAlt: 0.2,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 8,
    startLat: -8.833221,
    startLng: 13.264837,
    endLat: -33.936138,
    endLng: 18.436529,
    arcAlt: 0.2,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 8,
    startLat: 49.2827,
    startLng: -123.1207,
    endLat: 52.3676,
    endLng: 4.9041,
    arcAlt: 0.2,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 8,
    startLat: 1.3521,
    startLng: 103.8198,
    endLat: 40.7128,
    endLng: -74.006,
    arcAlt: 0.5,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 9,
    startLat: 51.5072,
    startLng: -0.1276,
    endLat: 34.0522,
    endLng: -118.2437,
    arcAlt: 0.2,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 9,
    startLat: 22.3193,
    startLng: 114.1694,
    endLat: -22.9068,
    endLng: -43.1729,
    arcAlt: 0.7,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 9,
    startLat: 1.3521,
    startLng: 103.8198,
    endLat: -34.6037,
    endLng: -58.3816,
    arcAlt: 0.5,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 10,
    startLat: -22.9068,
    startLng: -43.1729,
    endLat: 28.6139,
    endLng: 77.209,
    arcAlt: 0.7,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 10,
    startLat: 34.0522,
    startLng: -118.2437,
    endLat: 31.2304,
    endLng: 121.4737,
    arcAlt: 0.3,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 10,
    startLat: -6.2088,
    startLng: 106.8456,
    endLat: 52.3676,
    endLng: 4.9041,
    arcAlt: 0.3,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 11,
    startLat: 41.9028,
    startLng: 12.4964,
    endLat: 34.0522,
    endLng: -118.2437,
    arcAlt: 0.2,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 11,
    startLat: -6.2088,
    startLng: 106.8456,
    endLat: 31.2304,
    endLng: 121.4737,
    arcAlt: 0.2,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 11,
    startLat: 22.3193,
    startLng: 114.1694,
    endLat: 1.3521,
    endLng: 103.8198,
    arcAlt: 0.2,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 12,
    startLat: 34.0522,
    startLng: -118.2437,
    endLat: 37.7749,
    endLng: -122.4194,
    arcAlt: 0.1,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 12,
    startLat: 35.6762,
    startLng: 139.6503,
    endLat: 22.3193,
    endLng: 114.1694,
    arcAlt: 0.2,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 12,
    startLat: 22.3193,
    startLng: 114.1694,
    endLat: 34.0522,
    endLng: -118.2437,
    arcAlt: 0.3,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 13,
    startLat: 52.52,
    startLng: 13.405,
    endLat: 22.3193,
    endLng: 114.1694,
    arcAlt: 0.3,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 13,
    startLat: 11.986597,
    startLng: 8.571831,
    endLat: 35.6762,
    endLng: 139.6503,
    arcAlt: 0.3,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 13,
    startLat: -22.9068,
    startLng: -43.1729,
    endLat: -34.6037,
    endLng: -58.3816,
    arcAlt: 0.1,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
  {
    order: 14,
    startLat: -33.936138,
    startLng: 18.436529,
    endLat: 21.395643,
    endLng: 39.883798,
    arcAlt: 0.3,
    color: colors[Math.floor(Math.random() * (colors.length - 1))],
  },
]

// Countries data (simplified version)
const countries = {
  features: [
    {
      type: "Feature",
      properties: { NAME: "Sample Country" },
      geometry: {
        type: "Polygon",
        coordinates: [[[0, 0], [1, 0], [1, 1], [0, 1], [0, 0]]]
      }
    }
  ]
}

let scene, camera, renderer, globe, controls
let animationId
let ringsInterval

const RING_PROPAGATION_SPEED = 3

function hexToRgb(hex) {
  const shorthandRegex = /^#?([a-f\d])([a-f\d])([a-f\d])$/i
  hex = hex.replace(shorthandRegex, function (m, r, g, b) {
    return r + r + g + g + b + b
  })

  const result = /^#?([a-f\d]{2})([a-f\d]{2})([a-f\d]{2})$/i.exec(hex)
  return result
    ? {
        r: parseInt(result[1], 16),
        g: parseInt(result[2], 16),
        b: parseInt(result[3], 16),
      }
    : null
}

function genRandomNumbers(min, max, count) {
  const arr = []
  while (arr.length < count) {
    const r = Math.floor(Math.random() * (max - min)) + min
    if (arr.indexOf(r) === -1) arr.push(r)
  }
  return arr
}

function initGlobe() {
  if (!canvasRef.value) return

  // Scene setup
  scene = new THREE.Scene()
  // No explicit fog here, if you want fog that doesn't obscure the globe,
  // it needs to be carefully tuned.
  // scene.fog = new THREE.Fog(0xffffff, 400, 2000)

  // Camera setup
  const aspect = canvasRef.value.clientWidth / canvasRef.value.clientHeight
  camera = new THREE.PerspectiveCamera(50, aspect, 180, 1800)
  camera.position.z = 500 // Adjusted for more distance between globe and text

  // Renderer setup
  renderer = new THREE.WebGLRenderer({
    canvas: canvasRef.value,
    alpha: true, // Keep alpha true for transparent background if needed
    antialias: true
  })
  renderer.setPixelRatio(window.devicePixelRatio)
  renderer.setSize(canvasRef.value.clientWidth, canvasRef.value.clientHeight)
  renderer.setClearColor(0xffffff, 0) // Clear color to transparent white

  // Lighting
  const ambientLight = new THREE.AmbientLight(globeConfig.ambientLight, 0.6)
  scene.add(ambientLight)

  const directionalLight1 = new THREE.DirectionalLight(globeConfig.directionalLeftLight, 1)
  directionalLight1.position.set(-400, 100, 400)
  scene.add(directionalLight1)

  const directionalLight2 = new THREE.DirectionalLight(globeConfig.directionalTopLight, 1)
  directionalLight2.position.set(-200, 500, 200)
  scene.add(directionalLight2)

  const pointLight = new THREE.PointLight(globeConfig.pointLight, 0.8)
  pointLight.position.set(-200, 500, 200)
  scene.add(pointLight)

  // Globe setup
  globe = new ThreeGlobe()
  scene.add(globe)

  // Configure globe material
  const globeMaterial = globe.globeMaterial()
  globeMaterial.color = new THREE.Color(globeConfig.globeColor)
  globeMaterial.emissive = new THREE.Color(globeConfig.emissive)
  globeMaterial.emissiveIntensity = globeConfig.emissiveIntensity
  globeMaterial.shininess = globeConfig.shininess

  // Setup globe data
  setupGlobeData()

  // Controls (basic mouse interaction)
  setupControls()

  // Start animation
  animate()

  // Setup rings animation
  setupRingsAnimation()
}

function setupGlobeData() {
  // Process arcs data
  const arcs = sampleArcs
  let points = []

  for (let i = 0; i < arcs.length; i++) {
    const arc = arcs[i]
    points.push({
      size: globeConfig.pointSize,
      order: arc.order,
      color: arc.color,
      lat: arc.startLat,
      lng: arc.startLng,
    })
    points.push({
      size: globeConfig.pointSize,
      order: arc.order,
      color: arc.color,
      lat: arc.endLat,
      lng: arc.endLng,
    })
  }

  // Remove duplicates
  const filteredPoints = points.filter(
    (v, i, a) =>
      a.findIndex((v2) =>
        ["lat", "lng"].every(
          (k) => v2[k] === v[k],
        ),
      ) === i,
  )

  // Configure globe
  globe
    .hexPolygonsData(countries.features)
    .hexPolygonResolution(3)
    .hexPolygonMargin(0.7)
    .showAtmosphere(globeConfig.showAtmosphere)
    .atmosphereColor(globeConfig.atmosphereColor)
    .atmosphereAltitude(globeConfig.atmosphereAltitude)
    .hexPolygonColor(() => globeConfig.polygonColor)

  globe
    .arcsData(sampleArcs)
    .arcStartLat((d) => d.startLat)
    .arcStartLng((d) => d.startLng)
    .arcEndLat((d) => d.endLat)
    .arcEndLng((d) => d.endLng)
    .arcColor((e) => e.color)
    .arcAltitude((e) => e.arcAlt)
    .arcStroke(() => [0.32, 0.28, 0.3][Math.round(Math.random() * 2)])
    .arcDashLength(globeConfig.arcLength)
    .arcDashInitialGap((e) => e.order)
    .arcDashGap(15)
    .arcDashAnimateTime(() => globeConfig.arcTime)

  globe
    .pointsData(filteredPoints)
    .pointColor((e) => e.color)
    .pointsMerge(true)
    .pointAltitude(0.0)
    .pointRadius(2)

  globe
    .ringsData([])
    .ringColor(() => globeConfig.polygonColor)
    .ringMaxRadius(globeConfig.maxRings)
    .ringPropagationSpeed(RING_PROPAGATION_SPEED)
    .ringRepeatPeriod(
      (globeConfig.arcTime * globeConfig.arcLength) / globeConfig.rings,
    )
}

function setupControls() {
  let isDragging = false
  let previousMousePosition = { x: 0, y: 0 }

  canvasRef.value.addEventListener('mousedown', (event) => {
    isDragging = true
    previousMousePosition = { x: event.clientX, y: event.clientY }
  })

  canvasRef.value.addEventListener('mousemove', (event) => {
    if (isDragging) {
      const deltaMove = {
        x: event.clientX - previousMousePosition.x,
        y: event.clientY - previousMousePosition.y
      }

      const deltaRotationQuaternion = new THREE.Quaternion()
        .setFromEuler(new THREE.Euler(
          deltaMove.y * 0.01,
          deltaMove.x * 0.01,
          0,
          'XYZ'
        ))

      globe.quaternion.multiplyQuaternions(deltaRotationQuaternion, globe.quaternion)
      previousMousePosition = { x: event.clientX, y: event.clientY }
    }
  })

  canvasRef.value.addEventListener('mouseup', () => {
    isDragging = false
  })

  canvasRef.value.addEventListener('mouseleave', () => {
    isDragging = false
  })
}

function setupRingsAnimation() {
  ringsInterval = setInterval(() => {
    if (!globe) return

    const newNumbersOfRings = genRandomNumbers(
      0,
      sampleArcs.length,
      Math.floor((sampleArcs.length * 4) / 5),
    )

    const ringsData = sampleArcs
      .filter((d, i) => newNumbersOfRings.includes(i))
      .map((d) => ({
        lat: d.startLat,
        lng: d.startLng,
        color: d.color,
      }))

    globe.ringsData(ringsData)
  }, 2000)
}

function animate() {
  animationId = requestAnimationFrame(animate)

  if (globe && globeConfig.autoRotate) {
    globe.rotation.y += globeConfig.autoRotateSpeed * 0.01
  }

  renderer.render(scene, camera)
}

function handleResize() {
  if (!camera || !renderer || !canvasRef.value) return

  const width = canvasRef.value.clientWidth
  const height = canvasRef.value.clientHeight

  camera.aspect = width / height
  camera.updateProjectionMatrix()
  renderer.setSize(width, height)
}

onMounted(() => {
  // Trigger entrance animation
  setTimeout(() => {
    isVisible.value = true
  }, 100)

  // Initialize globe
  setTimeout(() => {
    initGlobe()
  }, 500)

  // Handle window resize
  window.addEventListener('resize', handleResize)
})

onUnmounted(() => {
  if (animationId) {
    cancelAnimationFrame(animationId)
  }
  if (ringsInterval) {
    clearInterval(ringsInterval)
  }
  if (renderer) {
    renderer.dispose()
  }
  window.removeEventListener('resize', handleResize)
})
</script>

<style scoped>
canvas {
  display: block;
}
</style>