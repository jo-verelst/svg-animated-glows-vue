<template>
    <svg
      class="svg-glow"
      data-name="Layer 1"
      xmlns="http://www.w3.org/2000/svg"
      xmlns:xlink="http://www.w3.org/1999/xlink"
      width="400"
      height="400"
      viewBox="0 0 400 400"
    >
      <defs>
        <radialGradient
          :id="`radial-gradient${id}`"
          cx="200"
          cy="200"
          r="200"
          gradientUnits="userSpaceOnUse"
        >
          <stop offset="0" stop-color="#fff" />
          <stop offset="1" />
        </radialGradient>
        <mask :id="`mask${id}`" x="0" y="0" width="400" height="400" maskUnits="userSpaceOnUse">
          <circle cx="200" cy="200" r="200" :style="`fill: url(#radial-gradient${id})`" />
        </mask>
        <linearGradient
          :id="`linear-gradient${id}`"
          x1="336.6"
          y1="436.6"
          x2="63.4"
          y2="-36.6"
          gradientUnits="userSpaceOnUse"
        >
          <stop class="stop" offset="0.18" :stop-color="stopColor" />
          <stop class="start" offset="0.84" :stop-color="startColor" />
        </linearGradient>
      </defs>
      <title>svg-gradient</title>
      <g :style="`mask: url(#mask${id})`">
        <rect width="400" height="400" :style="`fill: url(#linear-gradient${id})`" />
      </g>
    </svg>
</template>
<script>
export default {
  name: "Glow",
  props: {
    startColor: String,
    stopColor: String
  },
  data() {
    return {
      id: Math.floor(Math.random() * Math.floor(10000000))
    }
  },
};
</script>