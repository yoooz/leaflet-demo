<template>
  <div id="map">
    <no-ssr>
      <!-- 気仙沼大島の緯度・経度 -->
      <l-map :zoom="zoom" :center="center">
        <l-tile-layer :url="url"></l-tile-layer>
        <l-marker v-for="marker of markers" :key="JSON.stringify(marker)" :lat-lng="marker"></l-marker>
      </l-map>
    </no-ssr>
  </div>
</template>

<script setup lang="ts">
// leafletの設定
const center = [38.856355, 141.615593]
const zoom = 13
const url = 'http://{s}.tile.osm.org/{z}/{x}/{y}.png'
// マーカーを置く場所一覧（観光地）
const markers = {
  center: [38.856355, 141.615593],
  kugunaribeach: [38.873171, 141.63164],
  mtkame: [38.87373, 141.617855],
  tatsumai: [38.830445, 141.624526],
  kodanobeach: [38.851971, 141.622216],
  bridge: [38.878459, 141.606309],
}
</script>

<style scoped>
#map {
  height: 100vh;
  width: 100vw;
}
</style>
