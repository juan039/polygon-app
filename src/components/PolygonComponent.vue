<template>
  <div class="polygon">
    <h2 class="m-4">Draw your polygon</h2>
    <p>
      Follow this steps.
    </p>
    <ul class="list-group m-4">
      <li class="list-group-item">
        Click anywhere inside the rainbow. This will create your starting point.
      </li>
      <li class="list-group-item">
        Click anywhere else inside the rainbow. This will create your first line.
      </li>
      <li class="list-group-item">Add as many points as you want for your polygon.</li>
      <li class="list-group-item">Click Complete to finish your polygon.</li>
      <li class="list-group-item">Click Reset to start over again.</li>
      <li class="list-group-item">Have Fun!</li>
    </ul>
    <svg width="500" height="500" @click="addPoint">
      <polygon
        v-if="isPolygon"
        :points="drawPoints"
        fill="none"
        stroke="red" />
      <polyline
        v-else
        :points="drawPoints"
        fill="none"
        stroke="red" />
    </svg>

    <div class="mt-4">
      <button type="button" class="btn btn-success m-1" @click="completePolygon">Complete</button>
      <button type="button" class="btn btn-secondary m-1" @click="resetPolygon">Reset</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PolygonComponent',
  data () {
    return {
      points: [],
      isPolygon: false
    }
  },
  computed: {
    drawPoints () {
      return this.points.join(' ')
    }
  },
  methods: {
    addPoint (e) {
      this.points.push([e.offsetX, e.offsetY])
    },
    completePolygon () {
      this.isPolygon = true
    },
    resetPolygon () {
      this.isPolygon = false
      this.points = []
    }
  }
}
</script>

<style scoped>
svg {
  box-shadow: rgb(85, 91, 255) 0px 0px 0px 3px, rgb(31, 193, 27) 0px 0px 0px 6px, rgb(255, 217, 19) 0px 0px 0px 9px, rgb(255, 156, 85) 0px 0px 0px 12px, rgb(255, 85, 85) 0px 0px 0px 15px;
}
</style>
